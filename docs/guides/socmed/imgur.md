# Authentication with Imgur

## Registering your Application

Imgur application creation can be accessed at [https://api.imgur.com/oauth2/addclient](https://api.imgur.com/oauth2/addclient).

- **Application Name:** Provide a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
- **Application Type:** Select "OAuth 2 authorization with a callback URL".
- **Application callback URL:** `https://your-site.com/auth/callback/imgur`
- **Application Website:** Enter your site's address, for instance `https://lorekeeper.me/`
- **Email:** Enter your email address.
- **Description:** Enter a brief description of your app.
    - For example: "Authenticates a Lorekeeper user with their Imgur account."

Your client secret will be shown after you create your application. Save this (temporarily!) or add it directly to your .env file as it will be hidden afterward; however, if need be you can generate a new secret.

## Connecting to Lorekeeper

The Imgur application portal can be accessed at [https://imgur.com/account/settings/apps](https://imgur.com/account/settings/apps).

You can access the client ID and (if necessary) generate a new client secret from this page.

In your .env file, add the lines:

```
IMGUR_CLIENT_ID=your_client_id_here
IMGUR_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.