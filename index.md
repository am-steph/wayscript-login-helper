# WayScript Genshin Login Helper Guide

# 1. Make a WayScript Account

[https://wayscript.com/](https://wayscript.com/)

# 2. Clone the Script

Go here and clone the script

[https://wayscript.com/script/6lWu3rLN](https://wayscript.com/script/6lWu3rLN)

![](https://i.imgur.com/Sk2tFQK.png)

# 3. Set up the time

![](https://i.imgur.com/1opHU82.png)

![](https://i.imgur.com/L8b7dQF.png)

# 4. Set up the secrets

Add the keys `OS_COOKIE` and `USER_AGENT`, the Discord webhook is optional, see at end of page for webhook instructions

![](https://i.imgur.com/oiL97tP.png)

Follow original taka guide to grab your cookie, use # to separate cookie for multi account, scroll further down to see cookie instructions.

[Cookie guide](https://am-steph.github.io/wayscript-login-helper/#getting-cookie-cloned-instructions)

These secret values are auto saved, no need to look for a save button

You can get your user agent like so:

![](https://i.imgur.com/4zXcZAU.png)

# 5. Run the script

![](https://i.imgur.com/40GtLZi.png)

If you get a failed sign-in or other error try these:
  - Log out and log back in
  - Ensure you are on the Daily Rewards page and not the HoyoLab forums
  - Try incognito mode
  - Try clearing your history/cache
  - Try using another browser

If all else fails, ask in #autocheckin-chat on Discord https://discord.com/invite/takagg

## Getting Cookie (Cloned instructions)
2. Go to the Daily Check-In event website https://webstatic-sea.mihoyo.com/ys/event/signin-sea/index.html?act_id=e202102251931481&lang=en-us
3. Log in with your MiHoYo/Genshin Impact account.  
   *If you have never checked in before, manually check in once to ensure that your cookies are set properly.*
4. Open the developer tools on your web browser (F12 on firefox/chrome)
5. Click on the "Console" tab
6. Type in `document.cookie` in the console
7. Copy the text output from the console  
   ![](https://imgur.com/eWP1OyO.png)

[Return to step 4](https://am-steph.github.io/wayscript-login-helper/#4-set-up-the-secrets)

### Multiple Accounts
Add a `#` immediately after the first cookie and paste the second cookie, no quotations and no spaces.

Do not log out of any account to grab another cookie, just open incognito and get cookie and close browser.

 - Remove any quotation marks "" at the front or end of the text 
    - Go back to the MiHoYo event website. You may close the tab but do not click the "Log Out" button because it may cause your cookie to expire.
    - **IF YOU WANT TO CHECK-IN MULTIPLE GENSHIN ACCOUNTS:**
    1. Paste your first cookie into the Value box on Wayscript.
    2. Open a new private browsing / Incognito window
    3. Go to the MiHoYo event website on your new browser instance, and log in with your second account
    4. Copy the `document.cookie` as before
    5. Go back to the Wayscript page, and type a hash `#` at the end of your first cookie
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
4. Go back to the ".secrets" tab and add a new secret called DISCORD_WEBHOOK.
   ![](https://i.imgur.com/oiL97tP.png)
5. Run the script again and check for message in the channel you set the webhook in
   ![](https://i.imgur.com/40GtLZi.png)
   ![](https://i.imgur.com/0FMvJHW.png)

To stop receiving Discord notifications, delete your DISCORD_WEBHOOK secret.
