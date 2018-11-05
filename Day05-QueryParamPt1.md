# [Day 5 - Query Parameters Part 1](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-5-query-parameters-part-1)

Use the query parameters covered today to filter, sort, and specify columns.  Navigate to the [Graph Explorer](https://aka.ms/ge).  Execute the following commands.

1. Get logged in user's high priority emails.
    - https://graph.microsoft.com/v1.0/me/messages?$filter=importance eq 'High'
1. Get name, size, and webUrl of logged in user's OneDrive site files.
    - https://graph.microsoft.com/v1.0/me/drive/root/children?$select=name,size,webUrl
1. Get logged in user's contacts sorted by birthday.
    - https://graph.microsoft.com/v1.0/me/contacts?$orderby=birthday 
