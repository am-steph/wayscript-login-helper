# WayScript Genshin Login Helper Guide

# Make a WayScript Account

[https://wayscript.com/](https://wayscript.com/)

# Clone the Script

Go here and clone the script

[https://wayscript.com/script/6lWu3rLN](https://wayscript.com/script/6lWu3rLN)

![](https://i.imgur.com/Sk2tFQK.png)

# Set up the time

![](https://i.imgur.com/1opHU82.png)

![](https://i.imgur.com/L8b7dQF.png)

# Set up the secrets

![](https://i.imgur.com/oiL97tP.png)

Follow original taka guide to grab your cookie, use # to separate cookie for multi account

These secret values are auto saved, no need to look for a save button

![](https://i.imgur.com/4zXcZAU.png)

# Run the script

![](https://i.imgur.com/40GtLZi.png)


## Getting Cookie (Cloned instructions)
2. Go to the Daily Check-In event website https://webstatic-sea.mihoyo.com/ys/event/signin-sea/index.html?act_id=e202102251931481&lang=en-us
3. Log in with your MiHoYo/Genshin Impact account.  
   *If you have never checked in before, manually check in once to ensure that your cookies are set properly.*
4. Open the developer tools on your web browser (F12 on firefox/chrome)
5. Click on the "Console" tab
6. Type in `document.cookie` in the console
7. Copy the text output from the console  
   ![](https://imgur.com/eWP1OyO.png)
   
 - Remove any quotation marks "" at the front or end of the text 
    - Go back to the MiHoYo event website. You may close the tab but do not click the "Log Out" button because it may cause your cookie to expire.
    - **IF YOU WANT TO CHECK-IN MULTIPLE GENSHIN ACCOUNTS:**
    1. Paste your first cookie into the Value box on GitHub, but do not click "Add Secret" yet.
    2. Open a new private browsing / Incognito window
    3. Go to the MiHoYo event website on your new browser instance, and log in with your second account
    4. Copy the `document.cookie` as before
    5. Go back to the GitHub page, and type a hash `#` at the end of your first cookie
    6. Paste your second cookie immediately after the `#` and remove the quotation marks "" if needed

## Discord Webhooks
This is an **OPTIONAL** step to let the script send you a notification on Discord whenever it runs a check-in.

Instructions provided by https://github.com/am-steph/genshin-impact-helper
1. Edit channel settings. (Create your own discord server or private channel for this)
   ![](https://i.imgur.com/Q0KFNzv.png)
2. Go into Integrations and view webhooks.
   ![](https://i.imgur.com/Z4pfACE.png)
3. Create a new webhook and copy the URL.
   ![](https://i.imgur.com/b3ZL3m3.png)
4. Go back to the "Secrets" tab on the repository and add a new secret called DISCORD_WEBHOOK.
   ![](https://i.imgur.com/YusKz6V.png)
5. Run the github action again and check for message in the channel you set the webhook in
   ![](https://i.imgur.com/0FMvJHW.png)

To stop receiving Discord notifications, delete your DISCORD_WEBHOOK secret.
