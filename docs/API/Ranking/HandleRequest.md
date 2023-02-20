# Handle Join Request [POST]

```/api/ranking/handlejoinrequest/```

This endpoint accepts or denies the provided join request.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `userId`       | The user who's join request you want to handle | `INTEGER` |
| `groupId`    | The group which you want to look for the join request | `INTEGER` | 
| `boolean`    | Should the join request be accepted? | `BOOLEAN` |

## Examples

=== "Javascript"
    ```javascript
    async function handleRequest() {
        const response = await fetch('https://api.roservices.app/api/ranking/handlejoinrequest', {
            method: 'POST',
            headers: {
            'Content-Type': 'application/json',
            'key': 'YOUR GAMEKEY HERE'
            },
            body: JSON.stringify({ userId: 'USER ID HERE', groupId: 'GROUP ID HERE', boolean: true/false })
        });
        return response.json();
    }
    ```

=== "Python"
    ```python
    import requests

    def handleRequest(userId, groupId, boolean):
        data = {'userId': userId, 'groupId': groupId, 'boolean': boolean} # Don't need to change anything here
        headers = {'content-type': 'application/json', 'key': 'PUT YOUR GAMEKEY HERE'}

        request = requests.post('https://api.roservices.app/api/ranking/handlejoinrequest', json=data, headers=headers)

        if request.status_code == 200:
            return request.json(), "f{userId} has been accepted into the group."
        else:
            return "Something went wrong!"
    '''
    Replace 1 with user id you want to accept
    Replace 2 with group id
    Replace true/false
    '''
    handleRequest(1, 2, true/false) 

    ```



=== "Luau"
    ```lua
    local HttpService = game:GetService("HttpService")
    local URL = "https://api.roservices.app/api/ranking/handlejoinrequest"
    local function request()
	local response = HttpService:RequestAsync(
		{
			Url = URL, 
			Method = "POST",
			Headers = {
				["Content-Type"] = "application/json",
                ["key"] = "YOUR GAMEKEY HERE"
			},
			Body = HttpService:JSONEncode({userId = "USER ID HERE", groupId = "GROUP ID HERE", boolean: true/false})
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
