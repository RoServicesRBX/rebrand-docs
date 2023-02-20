# Promote [POST]

```/api/ranking/promote/```

This endpoint promotes the specified user.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `userId`       | The user who you want to promote | `INTEGER` |
| `groupId`    | The group which the user is in | `INTEGER` | 

## Examples

=== "Javascript"
    ```javascript
    async function promote() {
        const response = await fetch('https://api.roservices.app/api/ranking/promote', {
            method: 'POST',
            headers: {
            'Content-Type': 'application/json',
            'key': 'YOUR GAMEKEY HERE'
            },
            body: JSON.stringify({ userId: 'USER ID HERE', groupId: 'GROUP ID HERE' })
        });
        return response.json();
    }
    ```



=== "Python"
    ```python
    import requests

    def promote(userId, groupId):
        data = {'userId': userId, 'groupId': groupId} # Don't need to change anything here
        headers = {'content-type': 'application/json', 'key': 'PUT YOUR GAMEKEY HERE'}

        request = requests.post('https://api.roservices.app/api/ranking/promote', json=data, headers=headers)

        if request.status_code == 200:
            return request.json(), "f{userId} Has been promoted successfully!"
        else:
            return "Something went wrong!"
    '''
    Replace 1 with user id
    Replace 2 with group id
    '''
    promote(1, 2) 

    ```


=== "Luau"
    ```lua
    local HttpService = game:GetService("HttpService")
    local URL = "https://api.roservices.app/api/ranking/promote"
    local function request()
	local response = HttpService:RequestAsync(
		{
			Url = URL, 
			Method = "POST",
			Headers = {
				["Content-Type"] = "application/json",
                ["key"] = "YOUR GAMEKEY HERE"
			},
			Body = HttpService:JSONEncode({userId = "USER ID HERE", groupId = "GROUP ID HERE"})
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