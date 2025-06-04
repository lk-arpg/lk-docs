# Authentication with Toyhou.se

## Registering your Application

Toyhou.se application creation can be accessed at [https://toyhou.se/~developer](https://toyhou.se/~developer).

1. Go to My Apps/[https://toyhou.se/~developer/apps](https://toyhou.se/~developer/apps)
2. Click "Create App"
3. Fill out the general information as appropriate to identify your app to your site's users.
    - It's recommended to provide a simple but descriptive name for your app, such as "Sitename" or "Sitename Lorekeeper".
4. Under "Developer information", supply the callback URL (`http://your-site.com/auth/callback/toyhouse`). You will need to list all variants of the URL as appropriate (`http` vs `https`, with and without `www`), separated by commas without any spaces, e.g.:
    - `http://www.your-site.com/auth/callback/toyhouse,http://your-site.com/auth/callback/toyhouse,https://www.your-site.com/auth/callback/toyhouse,https://your-site.com/auth/callback/toyhouse`
5. Click "Create". Your app will be created and your client ID and secret will be displayed.

## Connecting to Lorekeeper

Your client ID and secret can be accessed via your app's information, available via [https://toyhou.se/~developer/apps](https://toyhou.se/~developer/apps); click on the name of your app to view these and/or edit it.

In your .env file, add the lines:

```
TOYHOUSE_CLIENT_ID=your_client_id_here
TOYHOUSE_CLIENT_SECRET=your_client_secret_here
```

Replacing the `client_id` and `client_secret` with the ones from your application.