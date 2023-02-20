# Exile [POST]

```/api/ranking/exile/```

This endpoint exiles the specified user.

You need to open a ticket in our [Discord server](https://roservices.app/discord) to request the exile endpoint be enabled for your group.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `userId`       | The user who you want to exile | `INTEGER` |
| `groupId`    | The group which the user is in | `INTEGER` | 
| `token`    | Exile token | `STRING` | 

[How do I generate exile tokens?](/API/Tokens/GenToken/)  
[How does exile work?](/API/Explanations/Exile/)

