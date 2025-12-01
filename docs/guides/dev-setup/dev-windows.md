# Local Development Setup - Windows

## Overview

- **This guide assumes you are on Windows.** [Mac](local-setup/mac.md) and [Linux](local-setup/linux.md) have different methods.
- **Please read every step of this guide carefully.** It is highly recommend doing a full read-through before you even get started.

Within this guide, we will be installing the following software:

- [Composer](https://getcomposer.org) for handling PHP packages
- [VS Code](https://code.visualstudio.com) as our code editor

!!! info "Windows Firewall Pop-ups"
    At any point in time while installing the below software, you may see a pop-up like this. **Click "Allow" to allow the software to finish installing.** All of the recommended software is safe.

    <figure markdown="span">
    ![Windows Firewall pop-up](../../images/local-setup/windows/xampp-firewall.png){ width="600" }
    </figure>

## Copying Lorekeeper

We are now going to use Git Extensions to make a copy of Lorekeeper. This will be your personalized version that is posted to your live website.

1. In Git Extensions, select "Clone a Repository." "Clone" is the Git term for making a copy of the code.
(Ignore the button that says to specifically clone a GitHub Repository. That option is for advanced users who have GitHub accounts.) 

<figure markdown="span">
  ![clicking clone repository button in git extensions](../../images/local-setup/windows/clone-repo.png){ width="600" }
</figure>

2. Now we will fill out this field with some information that tells Git Extensions where the Lorekeeper code is located. On the browser, it can be access [here](https://github.com/lk-arpg/lorekeeper), but we use a slightly different URL address when pasting it into Git.

3. Paste `https://github.com/lk-arpg/lorekeeper.git` into the first text box labeled **Repository to clone**. Some data will begin to populate automatically -- that's good!

<figure markdown="span">
  ![clicking clone repository button in git extensions](../../images/local-setup/windows/clone-repo-1.png){ width="600" }
</figure>

4. Next, click "Browse". We are going to navigate to a specific directory within our installation of XAMPP. If you installed XAMPP in the directory `C:/xampp/`, we will be selecting the folder `C:/xampp/htdocs`. **If this folder does not exist, just type it in, and it'll be created for you.**

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-2.png){ width="600" }
</figure>

5. After clicking "Select Folder", your window should look like this.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-3.png){ width="600" }
</figure>

6. Click the dropdown next to "Branch" and select `main`. You also have to option to directly select the 3.0.0 version, but this can make things slightly more complicated later on. We will instead download LK v2 (aka `main`) and then update it to match v3.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-4.png){ width="600" }
</figure>

7. After that's selected, leave everything else as default. You can then click "Clone".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-5.png){ width="600" }
</figure>

8. A window like this will show up. Let it do its thing, then click "OK" when prompted.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-6.png){ width="600" }
</figure>

9. Click "Yes" to open the new repository now.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/clone-repo-7.png){ width="600" }
</figure>

10. It will open a screen like this. There's a lot of buttons here, but don't fret! We won't need most of them.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3.png){ width="600" }
</figure>

11. First, let's make sure we're updated to v3.0.0. On the left panel you'll see a dropdown labeled `origin`. Click that to create a further dropdown, then click `release`. You will see a branch labeled v3.0.0. A "branch" refers to a specific version of the code.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3-1.png){ width="600" }
</figure>

12. Right-click 'v3.0.0' and select "Fetch & Merge (Pull)".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3-2.png){ width="600" }
</figure>

13. You will see a similar window to before -- get used to it, this is what will be displayed every time you perform a git operation! Press "OK" when prompted.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3-3.png){ width="600" }
</figure>

14. This window will then appear. Leave everything as default, and select "Merge".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3-4.png){ width="600" }
</figure>

15. Press "OK" after this window finishes processing.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/update-v3-5.png){ width="600" }
</figure>

16. That's it! You now have a copy of Lorekeeper on your computer, updated to v3.0.0.

## Setting Up Lorekeeper

We need to install two more pieces of software before we can get our copy of Lorekeeper fully up and running.

### Installing Composer

1. First, we will install Composer, which handles installation of PHP packages. Go [here](https://getcomposer.org) and select "Download".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-1.png){ width="600" }
</figure>

2. Click the link for the Windows Installer, then run it.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-2.png){ width="600" }
</figure>

3. Click to install for all users.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-3.png){ width="600" }
</figure>

4. Leave developer mode **unchecked**. Click "Next".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-4.png){ width="600" }
</figure>

5. XAMPP should be automatically selected as your command line version of PHP. If not, use the dropdown to select it. If prompted, also select the checkmark to add it to your path.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-5.png){ width="600" }
</figure>

6. Click "Next" on this screen.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-6.png){ width="600" }
</figure>

7. You will see a screen similar to this one, summarizing your options. Click "Install".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-7.png){ width="600" }
</figure>

8. On this screen, click "Next".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-8.png){ width="600" }
</figure>

9. Then, click "Finish"!

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/composer-9.png){ width="600" }
</figure>

10. **Reboot your computer.** While Composer mentions that it won't always be necessary, rebooting our computer after installing Composer is the best way to prevent issues.

### Installing Visual Studio Code

Visual Studio Code is the piece of software we will use to edit our Lorekeeper files. (Pardon the sparse screenshots here, I already had it installed!)

!!! info "A Note for Advanced Users"

    You can install the VSCodium open source version, which comes with AI/Copilot features disabled by default, [here](https://github.com/VSCodium/vscodium/releases). However, you may run into issues with using certain extensions due to Microsoft's licensing. When in doubt, it is better to go with the Microsoft official release.

1. Go [here](https://code.visualstudio.com) to download it and press the big download button. (Fortunately, we can disable the recently added AI features.)

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/vscode-1.png){ width="600" }
</figure>

2. Run the newly downloaded file. You will be presented with the license agreement. Check the agree button, then click "Next".

3. Check all the boxes (with desktop icon checked depending on your preference) and click "Next".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/VSCodeUserSetup-x64-1.102.3.tmp_kvdkB3aTvY.png){ width="600" }
</figure>

4. Click "Install".

5. It will then install. Check the button to launch it, then click the "Finish" button when complete.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/VSCodeUserSetup-x64-1.102.3.tmp_YGV489RIgS.png){ width="600" }
</figure>

!!! info "Disabling AI Features"
    Microsoft constantly changes how to disable AI features within Visual Studio Code. As a result, unfortunately we can not provide up-to-date instructions. Please use your favorite search engine to find the latest way to disable these features.

    The Lorekeeper community does **not** encourage, promote, or endorse usage of AI tools.

## Running Lorekeeper

1. Open up the File Explorer and navigate to where Lorekeeper is installed on your computer. The easiest way to do this is via Git Extensions. Click "Repository" and then "File Explorer" in the top navigation.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-1.png){ width="600" }
</figure>

2. Right click anywhere in the empty space (make sure you don't have a file/directory selected!) and click "Open With Code".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-2.png){ width="600" }
</figure>

3. Behold! All of the files that make up your Lorekeeper. However, we need to install a few files before it will work properly. In the top bar, click "Terminal" and then "New Terminal".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-3.png){ width="600" }
</figure>

4. Type in `composer install`. A lot of text will go flying by as composer installs the various chunks of code required for LK to run.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-4.png){ width="600" }
</figure>

**It may get stuck for a while on `Generating optimized autoload files`. Be patient! It will finish eventually.**

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-5.png){ width="600" }
</figure>

It should look like this when done:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-6.png){ width="600" }
</figure>

5. Next, we will create the .env file, which will define some variables that Lorekeeper needs to run. Right-click near the bottom of the file list and click "New File". Name this file `.env`.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-7.png){ width="600" }
</figure>

6. The file should open by default (if not, double click it to open it). You will see a screen like this:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-8.png){ width="600" }
</figure>

8. **We're going to paste a lot of text here!** Here is the contents to paste into this file:

```
APP_NAME=Lorekeeper
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

CONTACT_ADDRESS=
DEVIANTART_ACCOUNT=
 
LOG_CHANNEL=stack
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=lorekeeper
DB_USERNAME=root
DB_PASSWORD=

BROADCAST_DRIVER=log
CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

BROADCAST_DRIVER=log
CACHE_DRIVER=file
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=smtp
MAIL_HOST=smtp.mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_APP_CLUSTER=mt1

MIX_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
MIX_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"
```

9. Save the file. Now, go back to the terminal. We are going to run a few setup commands. Type in `php artisan key:generate`. You will see something like this:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-9.png){ width="600" }
</figure>

10. Next, type in `php artisan migrate`. This will populate the database with all of the tables that Lorekeeper needs to function. You'll see a LOT of text start to fly by. It should look like this when completed:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-10.png){ width="600" }
</figure>

!!! info "Adding MySQL to your PATH Variable"

    If you run into an error when running `php artisan migrate`, you may need to add MySQL to your computer's PATH variable.

    1. Open your start menu and search for "edit system environment variables".
    <figure markdown="span">
      ![start menu with edit environment variables selected](../../images/local-setup/windows/start-menu-edit-system-env-variables.png){ width="600" }
    </figure>

    2. Click "Environment Variables" in the pop-up.

    <figure markdown="span">
      ![start menu with edit environment variables selected](../../images/local-setup/windows/env-variables-popup.png){ width="600" }
    </figure>

    3. Under "System Variables", selected "Path" and then "Edit..."

    <figure markdown="span">
      ![selecting path and then clicking edit on system variables](../../images/local-setup/windows/system-variables-path-edit.png){ width="600" }
    </figure>

    4. Click "New".

    <figure markdown="span">
      ![selecting new on environment variables window](../../images/local-setup/windows/edit-env-variables-new.png){ width="600" }
    </figure>

    5. Type in the location of your MySQL bin folder. For example, if you followed our XAMPP guide, this will be located `C:\xampp\mysql\bin`. Click OK to save.

    <figure markdown="span">
      ![entering mysql path into environment variables window](../../images/local-setup/windows/entering-mysql-path.png){ width="600" }
    </figure>

    6. Restart Visual Studio Code as well as any other command prompts you have open for the changes to reflect.

11. Now for some Lorekeeper-specific commands. Run `php artisan add-site-settings` to populate the database with the site settings. It should look like this when completed:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-12.png){ width="600" }
</figure>

12. Then run `php artisan add-text-pages`. This will add the default text pages for LK:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-11.png){ width="600" }
</figure>

13. Next run `php artisan copy-default-images`. This will add the default images for various features on LK:

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/Code_elgj6mSNzn.png){ width="600" }
</figure>

14. Finally, we will run the command `php artisan setup-admin-user`. This will create user #1, the default admin account. The email and details you give it do not need to be real, but make them something you'll remember easily.

- `Proceed to create account with this information? (yes/no)` Answer **yes**.
- `Are you on a local/testing instance and not a live site? (yes/no)` Answer **yes**.
- `Would you like to mark your email address as verified and enter an alias now? (yes/no)` Answer **yes**.

The important details to mark as `yes` have been highlighted in red.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-13.png){ width="600" }
</figure>

15. Now, go to `http://localhost` in your browser. You can also access this by pressing the "Admin" button next to "Apache" in XAMPP.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-15.png){ width="600" }
</figure>

## Setup Complete

You have finished installing a local copy of Lorekeeper. You can login as the admin account you just set up, and begin trying out the different features.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/running-lk-14.png){ width="600" }
</figure>