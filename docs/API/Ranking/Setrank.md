# SetRank [POST]

```/api/ranking/setrank/```

This endpoint sets the rank of a specified user.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `userId`       | The user who's rank you want to change (id) | `INTEGER` |
| `groupId`    | The group which you want to look for the join request | `INTEGER` | 
| `rankId`    | The rank id you want the user ranked to | `INTEGER` |

## Examples

=== "Javascript"
    ```javascript
    async function setRank() {
        const response = await fetch('https://api.roservices.app/api/ranking/setrank', {
            method: 'POST',
            headers: {
            'Content-Type': 'application/json',
            'key': 'YOUR GAMEKEY HERE'
            },
            body: JSON.stringify({ user: 'USER ID HERE', group: 'GROUP ID HERE', rankid: 'RANK ID HERE' })
        });
        return response.json();
    }
    ```


=== "Python"
    ```python
    import requests

    def setRank(userId, groupId, rankId):
        data = {'userId': userId, 'groupId': groupId, 'rankId': rankId} # Don't need to change anything here
        headers = {'content-type': 'application/json', 'key': 'PUT YOUR GAMEKEY HERE'}

        request = requests.post('https://api.roservices.app/api/ranking/setrank', json=data, headers=headers)

        if request.status_code == 200:
            return request.json(), "f{userId} Has been ranked successfully!"
        else:
            return "Something went wrong!"
    '''
    Replace 1 with user id
    Replace 2 with group id
    Replace 3 with rank id
    '''
    setRank(1, 2, 3) 

    ```

=== "Luau"
    ```lua
    local HttpService = game:GetService("HttpService")
    local URL = "https://api.roservices.app/api/ranking/setrank"
    local function request()
	local response = HttpService:RequestAsync(
		{
			Url = URL, 
			Method = "POST",
			Headers = {
				["Content-Type"] = "application/json",
                ["key"] = "YOUR GAMEKEY HERE"
			},
			Body = HttpService:JSONEncode({userId = "USER ID HERE", groupId = "GROUP ID HERE", rankId: "RANK ID HERE"})
		}
	)
         if response.Success then
            print("Status code:", response.StatusCode, response.StatusMessage)
            print("Response body:\n", response.Body)
        else
            print("The request failed:", response.StatusCode, response.StatusMessage)
        end
    end
    
    local success, message = pcall(request)
    if not success then
        print("Http Request failed:", message)
    end
    ```