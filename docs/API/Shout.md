# Shout [POST]

```/api/ranking/shout/```

This endpoint shouts a specified message in the specified group.

## Request Body

| Body      | Description           | Type              |
| ----------- | ---------------------|--------------- |
| `groupId`    | The group which you want to shout in | `INTEGER` | 
| `message`    | The message you want posted on the shout | `STRING` |

## Examples

=== "Javascript"
    ```javascript
    async function shout() {
        const response = await fetch('https://api.roservices.app/api/ranking/shout', {
            method: 'POST',
            headers: {
            'Content-Type': 'application/json',
            'key': 'YOUR GAMEKEY HERE'
            },
            body: JSON.stringify({ group: 'GROUP ID HERE', message: 'SHOUT MESSAGE HERE' })
        });
        return response.json();
    }
    ```


=== "Python"
    ```python
    import requests

    def shout(groupId, message):
        data = {'groupId': groupId, 'message': message} # Don't need to change anything here
        headers = {'content-type': 'application/json', 'key': 'PUT YOUR GAMEKEY HERE'}

        request = requests.post('https://api.roservices.app/api/ranking/promote', json=data, headers=headers)

        if request.status_code == 200:
            return request.json(), "f{message} has been sent successfully!"
        else:
            return "Something went wrong!"
    '''
    Replace 1 with user id
    Replace message with what you want to shout
    '''
    shout(1, "message") 

    ```

=== "Luau"
    ```lua
    local HttpService = game:GetService("HttpService")
    local URL = "https://api.roservices.app/api/ranking/shout"
    local function request()
	local response = HttpService:RequestAsync(
		{
			Url = URL, 
			Method = "POST",
			Headers = {
				["Content-Type"] = "application/json" ,
                ["key"] = "YOUR GAMEKEY HERE"
			},
			Body = HttpService:JSONEncode({group = "GROUP ID HERE", message: "SHOUT MESSAGE HERE"})
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