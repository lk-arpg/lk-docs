# Authentication with Twitter

!!! warning "These instructions may be outdated or no longer functional."

In order to create an application for authentication using Twitter, you must first apply for a developer account.

## Apply for a Developer Account

The developer account application portal can be accessed at [https://developer.twitter.com/en/portal/petition/use-case](https://developer.twitter.com/en/portal/petition/use-case).

1. Select "Hobbyist" and then "Exploring the API".
2. You will be asked for basic information about yourself. Fill this out as appropriate.
3. You will be asked to describe how you will use the Twitter API and/or data.
    - Following is a sample text explaining Lorekeeper's use case; you may want to paraphrase this.
    - "I want to allow my users to authenticate using Twitter through the Laravel Socialite system. My site uses social media to verify the identity of users and/or to display their identitie(s) on said social media to other users, and I would like to provide Twitter as an option for my users."
    - Uncheck all the options below.
4. Review your answers and make any necessary adjustments.
5. Review the developer agreement & policy. Agree as you feel appropriate. If/when you are ready, submit your application.
6. You may be asked to verify your email; do so and the application review will begin.
7. Wait for review. You may be asked for further details; provide these as appropriate.

## Registering your Application

This section is incomplete pending more thorough documentation of the application registration process.

The Twitter developer portal can be accessed at [https://developer.twitter.com/en/portal/dashboard](https://developer.twitter.com/en/portal/dashboard).

1. (OPTIONAL) Click "Create Project".
    1. Give your project a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
    2. Select a use case; "Doing something else", for instance.
    3. Describe your project.
        - An example description could be something like "Allow users to authenticate with Lorekeeper site using Twitter through the Laravel Socialite system."
    4. Add an existing app or click "Create a new app instead".
2. Create your application. If you have not made a project, you may instead click "Projects & Apps" in the sidebar, then "Overview". Click "Create App" on this page.
    1. Give your app a simple but descriptive title, such as "Sitename" or "Sitename Lorekeeper".
    2. You will be shown your API Key, API Secret Key, and Bearer Token. These will only be shown now, so save them for use in your .env file.
        - Your API key is your client ID, while your API secret key is your client secret.
    3. Continue on to your app's dashboard.
        - You may regenerate your API Key and Secret via the "Keys and tokens" tab if necessary. **Note that doing so will break integration with Lorekeeper if you do not update your .env with the new information**.
    4. (Optional) Customize your app's details, such as uploading an icon for it.
    5. Scroll down to "Authentication settings". Click "Edit" for this section.
        1. Enable OAuth 1.0a via the provided toggle.
        2. **Callback URLs:** `https://your-site.com/auth/callback/twitter`
            - If you encounter issues, you may need to add variations with http and https, with and without www, and with and without a trailing slash (/).
        3. **Website URL:** `https://your-site.com`
        4. **Organization Name:** Enter your site's name.
        5. **Terms of Service:** `https://your-site.com/info/terms`
        6. **Privacy Policy:** `https://your-site.com/info/privacy`
        7. Click "Save".

## Connecting to Lorekeeper

Using the Key and Secret Key from earlier, add the following lines to your .env file:

```
TWITTER_CLIENT_ID=your_key_here
TWITTER_CLIENT_SECRET=your_secret_key_here
```