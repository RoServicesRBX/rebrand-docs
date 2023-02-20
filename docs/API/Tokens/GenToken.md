You need to open a ticket in our [Discord server](https://roservices.app/discord) to request the exile/token generation endpoint be enabled for your group.

# Generate Token [POST]

```/api/tokens/generate/```

This endpoint generates token.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `userId`       | The user | `INTEGER` |
| `groupId`    | The group which the user is in | `INTEGER` | 
| `type`    | Type (exile) | `STRING` | 