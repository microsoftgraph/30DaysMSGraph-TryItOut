# [Day 12 - Authentication and authorization scenarios](https://developer.microsoft.com/en-us/graph/blogs/30daysmsgraph-day-12-authentication-and-authorization-scenarios)

You can try the authorization code grant flow out using your browser and [Postman](https://www.getpostman.com/apps).  If you are not familiar with Postman or similar REST endpoint development tools feel free to revisit these exercises after you've gone through tomorrow's post for Day 13.

1. Register an Azure AD V2 app following the directions from Day 9.
    - Ensure that the redirect URI is https://localhost:8080 to match the below steps.
1. Open Postman and create a new POST request to https://login.microsoftonline.com/YOUR_TENANT_ID/oauth2/v2.0/token, replacing ‘YOUR_TENANT_ID’ with your tenant ID from your app registration.
1. Configure the Body tab as follows:
    - Choose ‘x-www-form-urlencoded’
    - Add a ‘client_id’ key and put your application ID from your app registration in the value
    - Add a ‘client_secret’ key and put your application secret from your app registration in the value
    - Add a ‘redirect_uri’ key and put ‘https://localhost:8080’ in the value
    - Add a ‘grant_type’ key and put ‘authorization_code’ in the value.
    - Add a ‘scope’ key and put ‘openid profile offline_access User.Read’ in the value.
    - Add a ‘code’ key and leave the value blank.
1. Open your browser and go to https://login.microsoftonline.com/YOUR_TENANT_ID/oauth2/v2.0/authorize?client_id=YOUR_APP_ID&response_type=code&redirect_uri=https%3A%2F%2Flocalhost%3A8080&response_mode=query&scope=openid%20profile%20offline_access%20User.Read, replacing ‘YOUR_TENANT_ID’ with your tenant ID and ‘YOUR_APP_ID’ with your application ID from your app registration.
1. Login and authorize the app. Your browser redirects back to https://localhost:8080 and should show an error that the site cannot be reached.
1. Copy the URL in the address bar of your browser and paste it into Notepad. It should look like https://localhost:8080/?code=IAQABAAIAAAC...&session_state=.... Copy all of the characters after code= and before &session_state. This is the authorization code returned by Azure.
1. Paste the authorization code into the ‘code’ key in Postman, then send the request.
1. The response contains a JSON payload with the access token, refresh token, and ID token.