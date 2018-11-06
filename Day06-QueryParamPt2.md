# [Day 6 - Query Parameters Part 2](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-6-query-parameters-part-2)

Use query parameters we covered today to count, search, expand, and restrict results.  Navigate to the [Graph Explorer](https://aka.ms/ge).  Execute the following commands.

1. Get number of contacts for the logged in user
    - https://graph.microsoft.com/v1.0/me/contacts?$count=true
1. Get the logged in user's OneNote notebooks, 2 per page
    - https://graph.microsoft.com/v1.0/me/onenote/notebooks?$top=2
1. Get the logged in user's emails starting with the 11th email
    - https://graph.microsoft.com/v1.0/me/messages?$skip=10
1. Get the logged in user's emails that contain the word "Contoso" in the message body
    - https://graph.microsoft.com/v1.0/me/messages?$search="body:Contoso"
1. Get expanded information for logged in user's manager
    - https://graph.microsoft.com/beta/me?$expand=manager
