# AS OF MAY 2023 WAYSCRIPT IS NO LONGER FREE (READ BELOW)

As wayscript is moving to a paid model, they only offer a free trial, not perpetually free.
It is advised to move to somewhere more stable like Amazon AWS, Google GCP, or Microsoft Azure and use their free tiers

The following is the basic code for doing logins, you may have to adapt the code for certain platforms and install/package the required libraries as needed.
```
import genshin
import os
import asyncio
from discord_webhook import DiscordWebhook, DiscordEmbed

async def login():
     client = genshin.Client(game=genshin.Game.GENSHIN)
     client.set_cookies(ltuid=os.environ.get('ltuid'), ltoken=os.environ.get('ltoken'))
     try:
          reward = await client.claim_daily_reward()
          return f"Claimed {reward.amount} x {reward.name}"
     except genshin.AlreadyClaimed:
          return "Reward already claimed"
     except:
          return "Error claiming reward"

def main():
     webhook = DiscordWebhook(url=os.environ.get('webhook'))
     response = asyncio.run(login())
     embed = DiscordEmbed(title="Genshin Daily Check-In",description=response)
     webhook.add_embed(embed)
     response = webhook.execute()
```

I'm not able to provide extensive support, but for general inquries, I can be reached at Stephanos#0001 in any of these genshin servers.
-  [Ganyu Mains](https://discord.gg/ganyumains)
-  [KQM Keqing Mains](https://discord.gg/keqing)
-  [Ayaka Mains](https://discord.gg/3fYHhvSCfq)
-  [Raiden Mains](https://discord.gg/aEzF9fFjSf)
-  [Kokomi Mains](https://discord.gg/kokomi)
-  [Eula Mains](https://discord.gg/sDykTKNxvz)
-  [Shenhe Mains](https://discord.gg/W2ZZtwcu8G)

# READ FIRST
~~The old Wayscript Viz has been discontinued as of August 6 2022, all existing workflows will be stopped and cease to function, the new Wayscript guide is located over [here](https://am-steph.github.io/wayscript-login-helper/wayscriptx)~~

~~https://am-steph.github.io/wayscript-login-helper/wayscriptx~~

## Honkai
For honkai, you can use the following:

https://app.wayscript.com/lairs/f69b434f-210f-4255-be61-e3b5b3e2a81d/public

Inside secrets, add the values `ltoken` and `ltuid` with their respective values from the cookie and nothing else

In the cron task, for the command use `python task.py`

I will not be providing extensive support for Honkai outside basic functionality of doing the check-in, you are free to clone and edit the script in order to add other functionality like Discord Webhooks and other push notifications. I will not be assisting or providing any help if you are attempting to moddify or add parts to the original script, it is expected you have coding knoweldge to some extent or know what you are doing when you do it.

---
---
---
---
---
---
---
---
---
---
---
---

# Genshin Impact Check-In Helper

[Daily Check-In](https://webstatic-sea.mihoyo.com/ys/event/signin-sea/index.html?act_id=e202102251931481&lang=en-us)

# Running Locally

Check out napkatti fork on setting variables and running locally
[napkatti fork](https://github.com/napkatti/genshin-impact-helper/tree/master)

# Heroku (Deprecated)

## Requirements
You will need to install Git and Heroku if you wish to use Heroku for the login helper.

[Git Downloads](https://git-scm.com/downloads)

[Heroku Signup](https://signup.heroku.com/)

[Heroku CLI](https://devcenter.heroku.com/articles/getting-started-with-python#set-up)

Follow the instructions and sign into Heroku after installing the CLI from either command prompt or terminal whichever you use.

A GitHub account is not required/needed to clone this repo, you only need a Heroku account.

## Usage

1. Clone this branch

This will create a new folder `genshin-impact-helper` in the working directory path you executed the command, when you first open command prompt it'll usually take you to `C:\Users\YOUR-NAME`, you can type `start .` in command prompt to see where it will be cloned.

```
git clone --branch heroku https://github.com/am-steph/genshin-impact-helper.git
```


2. Create a Heroku App

  [Heroku Dashboard](https://dashboard.heroku.com/apps)

  You can either create a app from your Heroku dashboard or just run `heroku create`

  ![](https://i.imgur.com/iqbP3Ah.png)


3. Follow instructions in app dashboard to deploy your code to Heroku

  ![](https://i.imgur.com/v0fgQ31.png)

  Login to Heroku if you haven't already. It should bring up a webpage to login.
  ```
  heroku login
  ```
  Navigate to your project folder, in this case we change to `genshin-impact-helper`. Add appropriate git remote according to your app name.
  ```
  cd genshin-impact-helper
  git init
  heroku git:remote -a genshin-helper-test  #Here im using genshin-helper-test as a example, change this to your Heroku app name
  ```

  ```
  git add .
  git commit -am "initial commit"
  git push heroku master
  ```


4. Next we need to grab our cookie

  To get your cookie go to the Daily Check-In event website https://webstatic-sea.mihoyo.com/ys/event/signin-sea/index.html?act_id=e202102251931481&lang=en-us

  Log in with your MiHoYo/Genshin Impact account.  
   *If you have never checked in before, manually check in once to ensure that your cookies are set properly.*

   Open the developer tools on your web browser (F12 on firefox/chrome)

   Click on the "Console" tab

   Type in `document.cookie` in the console
   
5. Copy the text output from the console  
   ![](https://imgur.com/eWP1OyO.png)

6. Next we need to set up environment variables, navigate to settings and click Reveal Config  Vars

   ![](https://i.imgur.com/5fBviLV.png)

   Enter `USER_AGENT` in KEY and `Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:87.0) Gecko/20100101 Firefox/87.0` in VALUE and click Add.
   
    ![](https://i.imgur.com/U592b4t.png)

7. Enter `OS_COOKIE` in KEY and paste in your copied cookie in VALUE

  ![](https://i.imgur.com/POIwX3J.png)
    
    **IF YOU WANT TO CHECK-IN MULTIPLE GENSHIN ACCOUNTS:**
    1. Paste your first cookie into the Value box on Heroku, but do not click "Add" yet.
    2. Open a new private browsing / Incognito window
    3. Go to the MiHoYo event website on your new browser instance, and log in with your second account
    4. Copy the `document.cookie` as before
    5. Go back to the Heroku page, and type a hash `#` at the end of your first cookie
    6. Paste your second cookie immediately after the `#` and remove the quotation marks "" if needed
    7. Click "Add"


  You can always click the pencil icon later on to edit your OS_COOKIE value if you want to add another account

  If you wish to add a Discord webhook to receive notifications when the login helper runs, you can add another key value `DISCORD_WEBHOOK`. Look at the end of the page to see where you can get your webhook.

8. Go to Resources tab and add the Heroku Scheduler add-on, don't worry this is free

  ![](https://i.imgur.com/q8GXou0.png)
  ![](https://i.imgur.com/zYpVcBN.png)
  ![](https://i.imgur.com/7SP6tQu.png)

9. Create a new job, set it to run everyday at the time you wish (time is in UTC)

  ![](https://i.imgur.com/sbYkhcX.png)

  For the command, put `python run.py`

  ![](https://i.imgur.com/Co9dyvP.png)

If you want to test to see if your script will run go back to your command window and type `heroku run bash`. After you are loaded in, type `python run.py` and check.

![](https://i.imgur.com/MCPBp6J.png)

**If you no longer want to check in automatically, you can disable/delete the scheduler**


## Discord Webhooks
This is an **OPTIONAL** step to let the script send you a notification on Discord whenever it runs a check-in.

1. Edit channel settings. (Create your own discord server or private channel for this)
   ![](https://i.imgur.com/Q0KFNzv.png)
2. Go into Integrations and view webhooks.
   ![](https://i.imgur.com/Z4pfACE.png)
3. Create a new webhook and copy the URL.
   ![](https://i.imgur.com/b3ZL3m3.png)
4. Go back to the "Settings" tab on the app and add a new KEY called DISCORD_WEBHOOK and paste in the URL.

To stop receiving Discord notifications, delete your DISCORD_WEBHOOK secret.


