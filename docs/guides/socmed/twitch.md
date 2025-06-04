# Authentication with Twitch

Note that you must have two-factor authentication enabled on your Twitch account to create an application.

## Registering your Application

Twitch application creation can be accessed at [https://dev.twitch.tv/console/apps/create](https://dev.twitch.tv/console/apps/create).

- **Name:** Provide a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
- **OAuth Redirect URLs:** `https://your-site.com/auth/callback/twitch`
    - Note that redirect URLs **must** use `https` unless you are using localhost
    - For local testing, use `http://localhost/auth/callback/twitch`
- **Category:** Select "Website Integration".

## Connecting to Lorekeeper

The Twitch application portal can be accessed at [https://dev.twitch.tv/console/apps](https://dev.twitch.tv/console/apps).

- Click on "Manage" for your application. Client ID and secret are shown at the bottom of this page.
- You will need to click "New Secret" to generate your client secret the first time. **Note that clicking it after will break integration with Lorekeeper if you do not update your .env with the new secret**.

In your .env file, add the lines:

```
TWITCH_CLIENT_ID=your_client_id_here
TWITCH_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.