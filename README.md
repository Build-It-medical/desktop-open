### GPWidget Executable

This app is setup to launch on port 3001 in dev. This is so it doesn't conflict with the dev sst frontend on 3000. It can be changed if necessary but it just should not be set to 3000.

The executable will persist authorization on the users device. When the access token is invalid due to time or corruption the executable will automatically try and refresh the token and if that fails it will display the login screen to the user

The SST application is setup to host the usermanagement api on a custom domain, this is auth.gpwidget.com in prod and `${stack.stage}-gpwidget.auth.builditmedical.tech` in development. Add this as AUTH_ENDPOINT in a .env file in the project root.

In .env we need one other variable `AUTH_PAGE` this should point to where we're redirecting, i.e. the GPWidget web app. In local this can be `http://localhost:3000` so it will point to your local instance of the sst frontend. In prod it should be https://app.gpwidget.com

It is important to note that this executable will only work with version v0.2.0 of the sst application which is currently on branch `support-executable`. (Remove this when stable and in use, just highlight minimal working version of sst app)
