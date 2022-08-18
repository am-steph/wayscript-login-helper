# Wayscript X Guide

Wayscript has been developing a new platform called Wayscript X, as such the old Wayscript is now called Wayscript Viz. Wayscript Viz is deprecated and will not be receiving updates or optimizations

As for the future of Wayscript Viz, I am not sure, thus I am making a guide for Wayscript X, without further ado lets get started

# 1. Make a Wayscript X Account
Yes I know you made one before, but you'll have to make it again. (Don't ask me, I didn't design this platform)

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

[For those who need reminder](https://am-steph.github.io/wayscript-login-helper/#4-set-up-the-secrets)


Once added, secrets cannot be viewed or edited, they can only be deleted and made again. If you wish to add additional accounts at a later date, you will need to delete and readd OS_COOKIE with both cookies.
![](https://i.imgur.com/KbG0E9b.png)

# 4. Set up your trigger

Go back to overview and click on Open Full Editor

![](https://i.imgur.com/bRwBU0i.png)
![](https://i.imgur.com/t9kyXSg.png)

Create a new cron trigger
Use `python genshin-os.py` as the command to run
![](https://i.imgur.com/IV0iLu0.png)
![](https://i.imgur.com/YDcVPxl.png)

***
### Note: To avoid random errors, its recommended to set your time between 05:00-22:00 UTC 
***

You will need to set a Crontab time. If you don't know what it is, use this site to help.

[https://crontab.guru/](https://crontab.guru/)

The time is in UTC, you will need to convert your time to UTC if you want it to activate at a certain time locally to you

Here it is set as 30 17 which is `17:30 UTC` or `12:30 EST` 

```
Translation:
30    min
17    th hour
*     every day of the month
*     every month
*     every day of the week

It will trigger at 17:30 every day in UTC time
```
```
e.g

```

## 5. Try to run it

At the bottom, there is a terminal, type in `python genshin-os.py` and enter

![](https://i.imgur.com/y1cICkF.png)
![](https://i.imgur.com/lnC9NoA.png)

There is a random sleep when it does the login, so it will inform you that it is sleeping for x amount of time. Because of this sometimes you could be unlucky and will have to wait a few minutes. If you want it to go a bit quicker, use `ctrl+c` to exit, press the up arrow, then `enter` again to run, hopefully the random sleep is shorter

Wait for the login to complete, if it says successfully signed in, then the login works, proceed to next steps

If it shows a cookie error, its possible the secrets values haven't been loaded in, kill the terminal and wait for it to start a new one and try again
![](https://i.imgur.com/Wg0qxLW.png)
![](https://i.imgur.com/sqnEmfv.png)

## 6. Deploy
Click on rocket then click `Deploy`

![](https://i.imgur.com/UJbdZLF.png)

# FAQ

### Can I set up Discord Webhooks like the previous one
Yes, refer to [this](https://am-steph.github.io/wayscript-login-helper/#discord-webhooks).  Put `DISCORD_WEBHOOK` in the secrets like the previous one (ignore the UI difference, put it in the same place you put OS_COOKIE and USER_AGENT)

### Does it run when I close the tab
Yes, please stop asking

### Its not working HALP
Check the `#autocheckin-chat` channel in TakaGG Discord

### How do I setup multiple accounts
Add `#` inbetween the cookies cookie1#cookie2

![](https://i.imgur.com/kYRZlF1.png)

(No these are not real cookies for any accounts, don't bother typing them out)

### How much time are we alloted on Wayscript X

I do not know. If you don't know what this means, then it probably won't matter.

### Can others see my code and secrets
No, other people won't be able to access your code or see your secrets, when shared or cloned secrets are discarded. Under publish you may have noticed that it says others with link to view and clone, as long as you don't click publish, they won't see anything. Even if it is published, the secrets are discarded when cloned.

![](https://i.imgur.com/wbw6CET.png)

### How to get cookie / Not working / ???

Read carefully and follow the instructions.

If all else fails, ping @Stephanos#0001 in the TakaGG Discord on `#autocheckin-chat`

I will only be responding to inquries that are not in the scopes of the FAQ or pinned messages, please check pinned messages in `#autocheckin-chat` for troubleshooting steps



