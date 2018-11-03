# [Day 3 - Graph Explorer](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-3-graph-explorer)

Navigate to the Graph Explorer.  Try the following calls to the Microsoft Graph using the demo tenant or logging into your own tenant.

1. Get logged in user - https://graph.microsoft.com/v1.0/me

Sample response:

```json
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users/$entity",
    "id": "48d31887-5fad-4d73-a9f5-3c356e68a038",
    "businessPhones": [
    "+1 412 555 0109"
    ],
    "displayName": "Megan Bowen",
    "givenName": "Megan",
    "jobTitle": "Auditor",
    "mail": "MeganB@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "12/1110",
    "preferredLanguage": "en-US",
    "surname": "Bowen",
    "userPrincipalName": "MeganB@M365x214355.onmicrosoft.com"
}
```

2. Get logged in user's manager - https://graph.microsoft.com/v1.0/me/manager

Sample response:

```json
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#directoryObjects/$entity",
    "@odata.type": "#microsoft.graph.user",
    "id": "24fcbca3-c3e2-48bf-9ffc-c7f81b81483d",
    "businessPhones": [
    "+1 205 555 0108"
    ],
    "displayName": "Diego Siciliani",
    "givenName": "Diego",
    "jobTitle": "CVP Finance",
    "mail": "DiegoS@M365x214355.onmicrosoft.com",
    "mobilePhone": null,
    "officeLocation": "14/1108",
    "preferredLanguage": "en-US",
    "surname": "Siciliani",
    "userPrincipalName": "DiegoS@M365x214355.onmicrosoft.com"
}
```