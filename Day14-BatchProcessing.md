# [Day 14 - Batch processing](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-14-batch-processing)

1. Create a batch request to get user profile picture, list of direct reports, list of calendar reminders for today.

    ```json
    {
    "requests": [
        {
        "id": "1",
        "method": "GET",
        "url": "/me/photo/$value"
        },
        {
        "id": "2",
        "method": "GET",
        "url": "/me/directReports"
        },
        {
        "id": "3",
        "method": "GET",
        "url": "/me/reminderView(startDateTime='2018-11-134T08:00:00.0000000', endDateTime='2018-11-134T17:00:00.0000000')",
        "headers": {
            "Content-Type": "application/json"
        }
        }
    ]
    }
    ```

1. Assuming you got a list of your direct reports, now you can build another batch request to check track their out of office settings. Below is a sample batch request.  Be sure to replace \<userID1@tenant\>, etc. with the actual user UPN values returned from above query  Ex. john@contoso.com.

    ```json
    {
        "requests": [
            {
                "id": "1",
                "method": "GET",
                "url": "/users/john@contoso.com<userID1@tenant>/mailboxSettings/automaticRepliesSetting"
            },
            {
                "id": "2",
                "method": "GET",
                "url": "/users/katie@contoso.com<userID2@tenant>/mailboxSettings/automaticRepliesSetting"
            },
            …
            …
        ]
    }
    ```