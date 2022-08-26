# Wayscript X Guide

Wayscript has been developing a new platform called Wayscript X, as such the old Wayscript is now called Wayscript Viz. Wayscript Viz is deprecated and will not be receiving updates or optimizations

*Update: Wayscript Viz as of August 6 has been shutdown for free users and will be completely shut down for all users by September, you should be using Wayscript X moving forward*

# 1. Make a Wayscript X Account
If you made one before for Wayscript Viz, you'll have to make it again. If you are new just make a account (Don't ask me, I didn't design this platform)

[https://app.wayscript.com/](https://app.wayscript.com/)

After setting up your account it'll ask you to make a workspace, just put in whatever

# 2. Clone the Script
Click Clone, it should clone into the workspace that you defined above earlier

[https://app.wayscript.com/lairs/ab4be66a-c414-4615-9a99-4a3f93e492e2/public](https://app.wayscript.com/lairs/ab4be66a-c414-4615-9a99-4a3f93e492e2/public)

# 3. Add secrets
![](https://i.imgur.com/99OrdMG.png)
![](https://i.imgur.com/rkA7aEM.png)
![](https://i.imgur.com/MaBQpkY.png)

*Need a reminder?*

**Ensure you are on the daily login page and not hoyolab forums page**

Anyone getting a sense of deja vu?

### Getting Cookie
1. Go to the Daily Check-In event website https://webstatic-sea.mihoyo.com/ys/event/signin-sea/index.html?act_id=e202102251931481&lang=en-us
2. Log in with your MiHoYo/Genshin Impact account.  
   *If you have never checked in before, manually check in once to ensure that your cookies are set properly.*
3. Open the developer tools on your web browser (F12 on firefox/chrome)
4. Click on the "Console" tab
5. Type in `document.cookie` in the console
6. Copy the text output from the console  
   ![](https://imgur.com/eWP1OyO.png)


You can get your user agent like so:

![](https://i.imgur.com/4zXcZAU.png)


Once added, secrets cannot be viewed or edited, they can only be deleted and made again. If you wish to add additional accounts at a later date, you will need to delete and readd OS_COOKIE with both cookies.
![](https://i.imgur.com/KbG0E9b.png)

# 4. Set up your trigger

Go back to overview and click on Open Full Editor

![](https://i.imgur.com/bRwBU0i.png)
![](https://i.imgur.com/ub4Ti1F.png)

Create a new cron trigger
Use `python genshin-os.py` as the command to run
![](https://i.imgur.com/IV0iLu0.png)
![](https://i.imgur.com/Q2vgn3z.png)

***
### Note: To avoid random errors, its recommended to set your time between 05:00-22:00 UTC 
***

You will need to set a Crontab time. If you don't know what it is, use this site to help.

[https://crontab.guru/](https://crontab.guru/)

The time is in UTC, you will need to convert your time to UTC if you want it to activate at a certain time locally to you

Here it is set as 30 15 which is `15:30 UTC` or `10:30 EST` 

```
Translation:
30    min
15    th hour
*     every day of the month
*     every month
*     every day of the week

It will trigger at 15:30 every day in UTC time
```
```
e.g
45 11 * * *     Run at 11:45 UTC every day, every month, and every day in the week
5 07 * * *      Run at 07:05 UTC every day, every month, and every day in the week 


Use the crontab.guru link to see what your cron setup translates too
Google a conversion from UTC time to your own local time to see what time it'll run
```

## 5. Try to run it

At the bottom, there is a terminal, type in `python genshin-os.py` and enter

![](https://i.imgur.com/y1cICkF.png)
![](https://i.imgur.com/lnC9NoA.png)

There is a random sleep when it does the login, so it will inform you that it is sleeping for x amount of time. Because of this sometimes you could be unlucky and will have to wait up to 5 minutes. If you want it to go a bit quicker, use `ctrl+c` to stop it from running, press the `up arrow`, then `enter` again to run, hopefully the random sleep is shorter

Wait for the login to complete, if it says successfully signed in, then the login works, proceed to next steps

If it shows a cookie error, its possible the secrets values haven't been loaded in, kill the terminal and wait for it to start a new one and try again
![](https://i.imgur.com/MR81xwE.png)
![](https://i.imgur.com/sqnEmfv.png)

## 6. Deploy
Click on rocket then click `Deploy`

![](https://i.imgur.com/UJbdZLF.png)

# FAQ

## Is there a Honkai version
For honkai, you can use the following:

https://app.wayscript.com/lairs/f69b434f-210f-4255-be61-e3b5b3e2a81d/public

Inside secrets, add the values `ltoken` and `ltuid` with their respective values from the cookie and nothing else

In the cron task, for the command use `python task.py`

I will not be providing extensive support for Honkai outside basic functionality of doing the check-in, you are free to clone and edit the script in order to add other functionality like Discord Webhooks and other push notifications. I will not be assisting or providing any help if you are attempting to moddify or add parts to the original script, it is expected you have coding knoweldge to some extent if you are going to edit it.

### Can I set up Discord Webhooks like the previous one
Yes, refer to [this](https://am-steph.github.io/wayscript-login-helper/#discord-webhooks).  Put `DISCORD_WEBHOOK` in the secrets like the previous one (ignore step 5 and use `python genshin-os.py` to run, put it in the same place you put OS_COOKIE and USER_AGENT)

### Does it run when I close the tab
Yes, please stop asking

### Its not working HALP
Check the `#autocheckin-chat` channel in [TakaGG Discord](https://discord.gg/takagg)

### How do I setup multiple accounts
Add `#` inbetween the cookies cookie1#cookie2

![](https://i.imgur.com/kYRZlF1.png)

(No these are not real cookies for any accounts, don't bother typing them out)

### How much time are we alloted on Wayscript X

According to Wayscript we are given 100 hours of runtime a month, this is more than plenty for the login script.

Assuming (5min of sleep + 1min runtime) x 31 days = ~180min a month or about 3hours out of 100hours, so its plenty enough

### Can others see my code and secrets
No, other people won't be able to access your code or see your secrets, when shared or cloned secrets are discarded. Under publish you may have noticed that it says others with link to view and clone, as long as you don't click publish, they won't see anything. Even if it is published, the secrets are discarded when cloned.

![](https://i.imgur.com/wbw6CET.png)

### How to get cookie / Not working / ???

Read carefully and follow the instructions.

If all else fails, ping @Stephanos#0001 in the [TakaGG Discord](https://discord.gg/takagg) on `#autocheckin-chat`

Please check pinned messages in `#autocheckin-chat` for troubleshooting steps or scroll up and read through the chat to see if someone else had your same issue, it will be faster than waiting around for a response. 

Alternatively I am also available on the following Genshin Discord servers, however there is no dedicated support channel for it, you could ping me in them to reach out:
-  [Ganyu Mains](https://discord.gg/ganyumains)
-  [KQM Keqing Mains](https://discord.gg/keqing)
-  [Ayaka Mains](https://discord.gg/3fYHhvSCfq)
-  [Raiden Mains](https://discord.gg/aEzF9fFjSf)
-  [Kokomi Mains](https://discord.gg/kokomi)
-  [Eula Mains](https://discord.gg/sDykTKNxvz)
-  [Shenhe Mains](https://discord.gg/W2ZZtwcu8G)




