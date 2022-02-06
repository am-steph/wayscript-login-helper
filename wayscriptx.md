# Wayscript X Guide

Wayscript has been developing a new platform called Wayscript X, as such the old Wayscript is now called Wayscript Viz. Wayscript Viz is deprecated and will not be receiving updates or optimizations

As for the future of Wayscript Viz, I am not sure, thus I am making a guide for Wayscript X, without further ado lets get started

## 1. Make a Wayscript X Account
Yes I know you made one before, but you'll have to make it again. (Don't ask me, I didn't design this platform)

https://app.wayscript.com/

After setting up your account it'll ask you to make a workspace, just put in whatever

## 2. Clone the Script
Click Clone, it should clone into the workspace that you defined above earlier

https://app.wayscript.com/lairs/ab4be66a-c414-4615-9a99-4a3f93e492e2/public

## 3. Add .secrets
![](https://i.imgur.com/eIhGwKY.png)

## 4. Add the environment variables
Anyone getting a sense of deja vu?

![For those who need reminder](https://am-steph.github.io/wayscript-login-helper/#4-set-up-the-secrets)

![](https://i.imgur.com/KbG0E9b.png)

## 5. Set up your trigger

Edit the time on the trigger

You will need to set a Crontab time. If you don't know what it is, use this site to help.

https://crontab.guru/

The time is in UTC, you will need to convert your time to UTC if you want it to activate at a certain time locally to you

Here it is set as `30 17 * * * ` which is `17:30 UTC` or `12:30 EST` 

```
Translation:
30    min
17    th hour
*     every day of the month
*     every month
*     every day of the week

It will trigger at 17:30 every day in UTC time
```
![](https://i.imgur.com/7Ngk895.png)

## 6. Try to run it

At the bottom, there is a terminal, type in `python genshin-os.py` and enter

Yes, you can click the Run button in the trigger to run it instead (continue reading for reason)

![](https://i.imgur.com/r9GvVfB.png)

There is a random sleep when it does the login, so it will inform you that it is sleeping for x amount of time. Because of this sometimes you could be unlucky and will have to wait a few minutes. If you want it to go a bit quicker, use `ctrl+c` to exit, press the up arrow, then `enter` again to run, hopefully the random sleep is shorter

Wait for the login to complete, if it says successfully signed in, then the login works, proceed to next steps

## 7. Deploy
Click on rocket then click `Deploy`

![](https://i.imgur.com/UJbdZLF.png)
