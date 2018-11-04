# [Day 4 - Request syntax](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-4-request-syntax)

Explore additional resources related to the Me (logged in user) entity and also add query parameters to filter the base query.  Navigate to the [Graph Explorer](https://aka.ms/ge) then execute the following commands:

1. Get logged in user's OneDrive site
    - [https://graph.microsoft.com/v1.0/me/drive](https://graph.microsoft.com/v1.0/me/drive)
1. Get users whose email address starts with "Adele"
    - [https://graph.microsoft.com/v1.0/users?\$filter=startswith(mail,'adele')](https://graph.microsoft.com/v1.0/users?$filter=startswith(mail,'adele'))
1. Get logged in user's user profile picture
    - [https://graph.microsoft.com/v1.0/me/photo/\$value](https://graph.microsoft.com/v1.0/me/photo/$value)
1. (Choose a new sample query by clicking show more samples from the left hand menu)