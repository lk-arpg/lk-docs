# Authenticating with Discord

## Registering your Application

Discord application creation can be accessed at [https://discord.com/developers/applications](https://discord.com/developers/applications).

1. Click on "New Application"
    - Give it a descriptive name, such as "Sitename" or "Sitename Lorekeeper".
2. You will be on the "General Settings" tab of your application. Use the sidebar to switch to the "OAuth2" tab.
3. Add the callback URL under "Redirects"
    - **Default callback URL:** `https://your-site.com/auth/callback/discord`
4. Remember to save your changes.

## Connecting to Lorekeeper

The Discord application portal can be accessed at [https://discord.com/developers/applications](https://discord.com/developers/applications).

You can find your application listed here once it's created. Click on it and navigate to the "OAuth2" tab via the sidebar to find the client ID and client secret on this page.

In your .env file, add the lines:

```
DISCORD_CLIENT_ID=your_client_id_here
DISCORD_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.