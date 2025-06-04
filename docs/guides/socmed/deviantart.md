# Authentication with deviantArt

Previously the only option for authentication, deviantArt remains available as an authentication option.

## Registering your Application

The deviantArt application portal can be accessed at [https://www.deviantart.com/developers/apps](https://www.deviantart.com/developers/apps).

1. Click on "Register your Application"
2. Give your application a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
    - This will be shown to users when they authenticate and in the user's authenticated apps (visible at [https://www.deviantart.com/settings/apps](https://www.deviantart.com/settings/apps)), so it's good policy to label it clearly.
3. Under "Application Settings", set:
    - **OAuth2 Redirect URI Whitelist (Required):** `https://your-site.com/auth/callback/deviantart`
    - **Original URLs Whitelist:** `https://your-site.com/auth/redirect/deviantart`
    - If you encounter issues, you may need to add variations with `http` and `https`, with and without `www`, and with and without a trailing slash (/).
    - If you have an existing dA application using `https://your-site.com` URLs, this should continue to work as before.
4. Click "Save". You do not need to publish your application.

## Connecting to Lorekeeper

Return to the [deviantArt application portal](https://www.deviantart.com/developers/apps).

Scroll to the application you just created. The `client_id` (visible by default) and `client_secret` (hidden, can be shown by pressing the button on the right hand side of the field) should be present. You will need these to connect Lorekeeper to your application.

In your .env file, add the lines:

```
DEVIANTART_CLIENT_ID=your_client_id_here
DEVIANTART_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.