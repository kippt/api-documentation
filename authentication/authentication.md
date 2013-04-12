# Authentication

Kippt's API requires authentication for some endpoints. You can use one of the following authentication methods.

## Browser session

You can access Kippt's API when you're logged into Kippt using regular browser session. Easiest way to test the API is to open GET endpoint in Chrome with [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc) extension installed.

__Note:__ JSONP is disabled for this authentication method.

## HTTP Basic Auth

HTTP Basic Auth, you know the drill. Use your Kippt credentials to authenticate. Email is accepted as username as well. [More information](http://en.wikipedia.org/wiki/Basic_access_authentication).

__Note:__ Try to avoid using using this method as Token Auth is usually much safer. And never store user's password on a server.

## Token Auth

You can authenticate with API token and your username. To authenticate with API token you need to supply required parameters as HTTP headers ```X-Kippt-Username``` and ```X-Kippt-API-Token```.

_Example:_ ```curl -X GET -H "X-Kippt-Username: jori" -H "X-Kippt-API-Token: 7fa721de1b0d1d918300a" https://kippt.com/api/clips/```

You can access the API token with ```/api/account/?include_data=api_token``` endpoint or get it from [developers.kippt.com](http://developers.kippt.com/#apitoken). You should always store user's API token instead of the password (first authenticate with HTTP Basic Auth, store the API token and use token authentication). API key can be reseted by changing your password.
