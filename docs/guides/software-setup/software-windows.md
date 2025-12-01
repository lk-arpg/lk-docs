# Local Software Setup - Windows

## Overview

- **This guide assumes you are on Windows.** [Mac](local-setup/mac.md) and [Linux](local-setup/linux.md) have different methods.
- **Please read every step of this guide carefully.** It is highly recommend doing a full read-through before you even get started.

Within this guide, we will be installing the following software:

- [XAMPP](https://www.apachefriends.org/download.html) for the local webserver and database
- [Git Extensions](https://gitextensions.github.io) for our graphical git client

!!! info "Windows Firewall Pop-ups"
    At any point in time while installing the below software, you may see a pop-up like this. **Click "Allow" to allow the software to finish installing.** All of the recommended software is safe.

    <figure markdown="span">
    ![Windows Firewall pop-up](../../images/local-setup/windows/xampp-firewall.png){ width="600" }
    </figure>

## XAMPP Setup

### Installing XAMPP

1. Download [XAMPP](https://www.apachefriends.org/download.html).

  - For LK v2, select **PHP 8.1**.
  - For LK v3.0 or above, select **PHP 8.2**.

<figure markdown="span">
  ![Downloading XAMPP](../../images/local-setup/windows/setup-xampp.png){ width="600" }
</figure>

2. Run the XAMPP .exe file. **If you see this warning, as long as you follow this guide, you can ignore it and just hit "OK".**

<figure markdown="span">
  ![XAMPP UAC Error](../../images/local-setup/windows/xampp-error.png){ width="600" }
</figure>

3. Click the "Next" button. You will then see this screen. We just want the defaults -- click "Next" again.

<figure markdown="span">
  ![XAMPP Installation Default Settings](../../images/local-setup/windows/xampp-defaults.png){ width="600" }
</figure>

4. Install XAMPP directly onto your C: drive. A good location is `C:\xampp`, which should also be the default. Then, click "Next".

<figure markdown="span">
  ![XAMPP Installation Directory](../../images/local-setup/windows/xampp-directory.png){ width="600" }
</figure>

5. Select your preferred language. This doesn't matter -- pick what's best for you.

<figure markdown="span">
  ![XAMPP Installation Language](../../images/local-setup/windows/xampp-language.png){ width="600" }
</figure>

6. Click "Next" on the following screen. 

<figure markdown="span">
  ![XAMPP Installation Ready to Install Screen](../../images/local-setup/windows/xampp-ready-to-install.png){ width="600" }
</figure>

7. XAMPP should now begin to install. This may take some time -- be patient!

<figure markdown="span">
  ![XAMPP Installating](../../images/local-setup/windows/xampp-installing.png){ width="600" }
</figure>

8. Once XAMPP has installed, check the box to start the control panel immediately (if it is not checked by default) and click "Finish".

<figure markdown="span">
  ![XAMPP Installation Finished](../../images/local-setup/windows/xampp-finished.png){ width="600" }
</figure>

9. Congrats! You now have XAMPP installed. Click "Start" next to Apache and MySQL.

<figure markdown="span">
  ![Starting Apache and MySQL](../../images/local-setup/windows/xampp-start.png){ width="600" }
</figure>

!!! info "Windows Defender Firewall Alert"
    If you are presented with a window like this for either application: Check both "Private" and "Public", then click "Allow Access". 
    
    This software is safe. You may need to click "Show More" to see these options.

    <figure markdown="span">
      ![Starting Apache and MySQL](../../images/local-setup/windows/uac-error.png){ width="600" }
    </figure>

### Configuring XAMPP

1. Next, we need to update the config files. Click "Config" next to Apache, and select `php.ini`.

<figure markdown="span">
  ![Opening the PHP.ini in XAMPP](../../images/local-setup/windows/xampp-php-ini.png){ width="600" }
</figure>

2. A file should open up in Notepad. We are going to change two values. First, use the search feature (Ctrl + F) or simply scroll down until you see `post_max_size`. This controls how large the files are that you can upload. Change this to `0` on your local *only*.

<figure markdown="span">
  ![Editing the post_max_size variable](../../images/local-setup/windows/xampp-post-max.png){ width="600" }
</figure>

3. The next value we change is `upload_max_filesize`. I like to change this to abnormally high on my local, but make it whatever feels right for you. To change it to 10 megabytes, for example, put a value of `10M`.

<figure markdown="span">
  ![Editing the upload_max_size variable](../../images/local-setup/windows/xampp-upload-max.png){ width="600" }
</figure>

4. Save your changes and close this file. We are going to edit one more config file.

5. Go back to XAMPP, click "Config", and select `httpd.conf`.

<figure markdown="span">
  ![Selecting the http.conf file](../../images/local-setup/windows/xampp-http-conf.png){ width="600" }
</figure>

6. Another file should open up in Notepad. We are going to change one value this time. Change whatever value is currently in `DocumentRoot` and the following `Directory` line to `C:/xampp/htdocs/lorekeeper/public`.

<figure markdown="span">
  ![Updating the DocumentRoot value](../../images/local-setup/windows/xampp-document-root.png){ width="600" }
</figure>

7. Save your changes and close this file. Then, click the "Stop" button next to Apache. After it **fully shuts downs**, click "Start" again.

<figure markdown="span">
  ![Stopping and starting XAMPP](../../images/local-setup/windows/xampp-stop-start.png){ width="600" }
</figure>

!!! info 
    Apache may fail to start if the folder `C:/xampp/htdocs/lorekeeper/public` does not exist. **This is OK.** Continue with this guide, and Apache will start after you have cloned LK.

8. Next, we are going to make one more change in anticipation of installing Lorekeeper. Click the "Admin" button next to MySQL.

<figure markdown="span">
  ![pressing the mysql admin button](../../images/local-setup/windows/mysql-admin.png){ width="600" }
</figure>

9. This will open a window similar to this in your browser. This is PHPMyAdmin, and it is where we control how most of the data is stored for Lorekeeper. Click "New".

<figure markdown="span">
  ![phpmyadmin front page](../../images/local-setup/windows/phpmyadmin-start.png){ width="600" }
</figure>

10. Type in `lorekeeper` or any other easy to remember name, then click "Create".

<figure markdown="span">
  ![creating a database in phpmyadmin](../../images/local-setup/windows/phpmyadmin-create.png){ width="600" }
</figure>

11. **Congratulations! We're done here for now.** Next, we will install the Git software needed to manage our Lorekeeper files.

## Installing Git Software

Historically, the software used for managing Git was Sourcetree, but I will be using **Git Extensions** as it is more stable and frequently updated.

### Installing Git

1. First, we need to install Git itself. Git is a tool used to manage files and file history for coding projects. Go [here](https://git-scm.com/downloads) to download the latest copy of Git.

Click this button...
<figure markdown="span">
  ![downloading git from the website](../../images/local-setup/windows/git-dl-1.png){ width="600" }
</figure>

..and then this link.
<figure markdown="span">
  ![clicking the second download link for git](../../images/local-setup/windows/git-dl-2.png){ width="600" }
</figure>

2. After the file is done downloading, run it. You will see this screen. Press "Next".

<figure markdown="span">
  ![git gnu license agreement](../../images/local-setup/windows/git-install.png){ width="600" }
</figure>

3. You may see a screen asking about a start menu folder. The default location (often "Git") is acceptable. Press "Next".

4. **Make sure the highlighted fields are selected.** Press "Next".

<figure markdown="span">
  ![a checklist of installation settings for git](../../images/local-setup/windows/git-install-1.png){ width="600" }
</figure>

5. This next option is up to you. Notepad++ (if you have it installed) or Notepad are both valid options.

<figure markdown="span">
  ![selecting your default text editor for git](../../images/local-setup/windows/git-install-2.png){ width="600" }
</figure>

6. For maximum compatibility with Lorekeeper, you will want to make sure you check "Override" and type in `main`.

<figure markdown="span">
  ![selecting your default branch name for git](../../images/local-setup/windows/git-install-3.png){ width="600" }
</figure>

7. You will then see this screen. Select the middle/"recommended" option.

<figure markdown="span">
  ![command line installation options for git](../../images/local-setup/windows/git-install-4.png){ width="600" }
</figure>

8. Select "OpenSSH".

<figure markdown="span">
  ![selecting default ssh option for git](../../images/local-setup/windows/git-install-5.png){ width="600" }
</figure>

9. Leave this option as whatever your computer detects as default.

<figure markdown="span">
  ![selecting how to handle SSL connections for git](../../images/local-setup/windows/git-install-6.png){ width="600" }
</figure>

10. Select "Checkout Windows-style, commit Unix-style line endings".

<figure markdown="span">
  ![selecting line ending conversion settings for git](../../images/local-setup/windows/git-install-7.png){ width="600" }
</figure>

11. Select "MinTTY".

<figure markdown="span">
  ![selecting the terminal editor for git](../../images/local-setup/windows/git-install-8.png){ width="600" }
</figure>

12. **This one is important. Select "fast-forward or merge".**

<figure markdown="span">
  ![selecting the terminal editor for git](../../images/local-setup/windows/git-install-9.png){ width="600" }
</figure>

13. Select "Git Credential Manager".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-install-10.png){ width="600" }
</figure>

14. Enable both file-system caching and symbolic links.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-install-11.png){ width="600" }
</figure>

15. You may be prompted with this screen. If so, **close all other windows on your computer** and then click "Install".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-install-12.png){ width="600" }
</figure>

16. Git will then begin to install. Be patient while it completes!

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-install-13.png){ width="600" }
</figure>

17. Congratulations! Git is now installed. Check "finish".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-install-14.png){ width="600" }
</figure>

18. **Reboot your entire computer.** Certain things we installed with Git will only take effect _after_ our computer has restarted. So do that, and then come back!

### Installing Git Extensions

You can use Git purely from the command line, but it's not reccomended for beginners. To make things easier, we will be using a tool called **Git Extensions**.

1. Go [here](https://gitextensions.github.io) and click "Download". 

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-dl.png){ width="600" }
</figure>

2. Scroll down and download the `.msi` file.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-dl-1.png){ width="600" }
</figure>

3. Run this file. You should be prompted with a window like this. Click "Next".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-1.png){ width="600" }
</figure>

4. You will be presented with two options. Select "Install for all users of this machine".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-2.png){ width="600" }
</figure>

5. Then, you will be asked for the installation directory. The default is perfectly acceptable.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-3.png){ width="600" }
</figure>

6. Click "Next" on this screen. We don't need to change any of the options.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-4.png){ width="600" }
</figure>

7. You may be presented with a "Telemetry Options" screen. What you choose here is up to you and your own privacy concerns.

8. Git Extensions will then begin installing. After it's done, you'll be sent to this screen. Click "Finish".

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-5.png){ width="600" }
</figure>

9. When starting Git Extensions, you may see this message. That's OK! We just need to install one more file. 

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/GitExtensions_p3zdwm14Fi.png){ width="600" }
</figure>

Click the button. It should open a webpage and automatic start the download of the .NET runtime. Run this file, and install it. It's a fairly straightforward install -- you shouldn't be presented with any funky options.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/net-runtime.png){ width="600" }
</figure>

10. Start Git Extensions again. You should be presented with the option to pick your language. I will be selecting English.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-language.png){ width="600" }
</figure>

11. Git Extensions will present you with this "checklist" window every time you start the software. **Not everything needs to be completed for it to run properly -- we will go through the essentials.**

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-checklist.png){ width="600" }
</figure>

12. Most options should be automatically marked as green. Please make a thread in the Lorekeeper discord if any of the options are not automatically detected. The option we are most concerned about is the second (configuring a username/email), which may or may not be green for you. Click that option.

<figure markdown="span">
  ![alt text](../../images/local-setup/windows/git-extensions-checklist-1.png){ width="600" }
</figure>

13. **Make sure the highlighted values are something you are OK with being seen by the public.** They are mandatory fields. All others can be left blank. Fill them in how you'd like, then select **Apply** then **OK**.

<figure markdown="span">
  ![setting a name and email in git extensions](../../images/local-setup/windows/git-extensions-checklist-2.png){ width="600" }
</figure>

14. A window like this should then open. **Congratulations! Git Extensions is now installed.**

<figure markdown="span">
  ![main screen of git extensions](../../images/local-setup/windows/git-extensions-installed.png){ width="600" }
</figure>

## Setup Complete

You have installed a local webserver and the software needed to handling Lorekeeper's code. You can now move onto [setting up your local copy of Lorekeeper](../setup-index.md#development-environment-set-up).