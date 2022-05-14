Today I learned about the Postman app. It's an incredible app to quickly perform integration testing on APIs.

It supports variables for easy parametrization.
For example, you can set up a `server_url` variable that switches depending on environment (dev, staging, prod).
Then you can parametrize your URLs with that variable.

You can also set up 2-line scripts to fill out variables from API responses.
For example here is a script to fill out the `api_token` variable based on the authentication endpoint response:

```
var jsonData = JSON.parse(responseBody);
postman.setEnvironmentVariable("api_token", jsonData.api_token);
```

There is one-line support for bearer tokens so authentication is really easy.
