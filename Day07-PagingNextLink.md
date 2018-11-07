# [Day 7 - Paging and NextLink](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-7-paging-and-nextlink)

Navigate to the [Graph Explorer](https://aka.ms/ge).  Execute the following commands.

1. Get the users from your organization’s directory
    - https://graph.microsoft.com/v1.0/users?$top=10
1. Get all the items in your OneDrive for Business
    - https://graph.microsoft.com/v1.0/me/drive/root/children?$top=5
1. Get all the items from a SharePoint Online Site list
    - https://graph.microsoft.com/v1.0/sites/m365x214355.sharepoint.com:/sites/HR:/lists/ed70c81d-fedf-4a1b-a1f1-f44e39c5bb78/items?$top=5000 
    - See appendix for details on how to build this Microsoft Graph query for SharePoint

## Appendix

How to get SharePoint List Items using Microsoft Graph

1. If you are not logged into the Graph Explorer (i.e. using a demo tenant) find out the name of the tenant.  Issue the following Microsoft Graph query:
    - https://graph.microsoft.com/v1.0/sites/root
    - Copy the **hostname** value from siteCollection entity, ex. "m365x214355.sharepoint.com"
1. Next you must use the site collection relative URL and find out the **id** of a list on that site. Issue below Microsoft Graph query to get those details:
    - https://graph.microsoft.com/v1.0/sites/<hostname value from step 1 above>:/\<relative path to site\>:/lists
        - Ex.  https://graph.microsoft.com/v1.0/sites/m365x214355.sharepoint.com:/sites/HR:/lists
    - Copy the **{id}** value from the first list record shown.
        - Ex. "id": "ed70c81d-fedf-4a1b-a1f1-f44e39c5bb78"
1. Next create Microsoft Graph query to fetch the top 5000 items (max that SharePoint can return in one page) from the list
    - https://graph.microsoft.com/v1.0/sites/<hostname value from step 1>:/\<relative path to site\>:/lists/<id value from step 2>/items?$top=5000
        - Ex. https://graph.microsoft.com/v1.0/sites/m365x214355.sharepoint.com:/sites/HR:/lists/ed70c81d-fedf-4a1b-a1f1-f44e39c5bb78/items?$top=5000
