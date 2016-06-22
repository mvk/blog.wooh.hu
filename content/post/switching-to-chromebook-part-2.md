+++
date        = "2016-06-15T18:56:42Z"
draft        = false
title       = "Switching to Chromebook - Part II."
description = "Switching to Chromebook"
tags		= [ "google", "chrome", "chromebook", "chromeos" ]
categories 	= [ "gadgets" ]
image		= "chromeos/toshiba/toshiba_header_2.jpg"
+++

In this part I'm going to show you a few applications I was using on a Mac and tell you how to migrate them to a Chromebook or what alternatives you can use if the application is not available at all for a Chromebook. <!--more-->

I thought I could compress everything in three small chunk post but it seems that's impossible. So expect a lot more blog posts from me on this specific topic.

# Recap

In case if you missed the previous post:

- [Switching to Chromebook - Part I.](/post/switching-to-chromebook-part-1/)

### HipChat

![HipChat](/images/chromeos/hipchat.png)

You're probably using the native HipChat app on your Mac. There is no native HipChat app for ChromeOS, but you can use the web version. You just need to login to **yourdomain.hipchat.com**, log-in and click on the *Launch the web app*.

![HipChat web app](/images/chromeos/hipchat_web.png)

it looks exactly the same as the native MacOS app. It's convenient. It will ask you to enable the Chrome desktop notifications which is useful. You can also configure not to notify you, or notify only if you're mentioned or only receive notifications from specific channels.

The web app has the same feeling as the native app. Same shortcuts, same UI.

### Slack

![Slack](/images/chromeos/slack_rgb.png)

The most powerful group chat client with awesome 3rd party integrations. There isn't any mentionable difference between the native app and the web app. You also need to enable the desktop notifications in Chrome to receive notifications. You can also switch between different slack accounts like in the native app.

https://slack.com

### Twitter

I'm a hardcore twitter user, so twitter is mandatory for me. I was using [TweetDeck by Twitter](https://itunes.apple.com/us/app/tweetdeck-by-twitter/id485812721?mt=12) on my Mac and I was a bit afraid what I can use after switching to Chromebook.

![Twitter](/images/chromeos/twitter.png)

I have pretty good news! Tweetdeck has a web app too, which looks exactly the same as the TweedDeck by Twitter app for mac. Except it does not eat up a lot of memory. You couldn't even recognize that this is not the Mac app.

https://tweetdeck.twitter.com

### Evernote

I'm a [Getting Things Done](http://gettingthingsdone.com/) addict. My wife grew up in Japan, so she loves to plan every second of our life. In 10 years I had to learn how to plan and how to be more productive. I use [Evernote](https://evernote.com) as my GTD tool of choice. Before Evernote I tried several things before. First I used [Things](https://culturedcode.com/things/) which only supported OS X and iOS. I need a tool for my phone too, so I migrated all my lists to [Wunderlist](https://www.wunderlist.com/) which was pretty awesome, but my wife was using Evernote so finally she convinced me to switch. 

![Evernote](/images/chromeos/evernote-logo.png)

The [Android](https://play.google.com/store/apps/details?id=com.evernote&hl=en) and [OS X](https://itunes.apple.com/us/app/evernote-capture-notes-sync/id281796108?mt=8) Evernote app is really good. It has a really good UI with all features you need for GTD.

Unfortunately the [Evernote Web Client](https://blog.evernote.com/blog/2015/08/13/introducing-the-new-evernote-web-client/) isn't that good, but luckily there is a *beta* version available. You can opt-in. Additionally Evernote has just introduced it's [Google Drive](https://evernote.com/google-drive/) support which is awesome!

Since all my documents are google documents on a Chromebook it's very convenient to use Evernote Beta Web Client and simply mix my notes in evernote with the google documents.

### Skype

Skype is a very popular IM and Video application. Skype keeps the world talking, for free. Share, message and call - now with group video on mobile and tablet too.

![Skype](/images/chromeos/skype.png)

There is no ChromeOS native app, but there is an alternative solution: Skype has an alternative [Skype for Web (Beta)](https://web.skype.com) application. You won't be able to make voice calls or video calls, but you can use Skype as an IM. I rarely used Skype for video/voice calls so I'm ok with this workaround.

But if you used Skype for voice and video calls, you need something else. The obvious choice is the [Google Hangouts](https://hangouts.google.com/). Nowadays almost everybody has a google account, but even without a google account, you can join a hangout meeting without the requirement of a Google account.

![Hangouts](/images/chromeos/hangouts.jpg)

There is also a native ChromeOS app available: [Google Hangouts](https://chrome.google.com/webstore/detail/google-hangouts/knipolnnllmklapflnccelgolnpehhpl?hl=en). Get it and try it out!

### Sublime 2, PyCharm and Vim

It's good to know, that there is no native ChromeOS IDE available at the moment. So no way to use Sublime or PyCharm or any well known editor. Sublime Text and PyCharm are available for OS X, Windows and Linux only.

You need to use a cloud IDE. At the first glance it sounds weird. Using a cloud editor? How? How can I manage/upload files there? Ohh boy, there are plenty of services out there. They are pretty good replacement for Sublime 2 and PyCharm.

### Cloud IDE

First, I read a lot of articles about the best cloud IDEs. There are around 10 in the market at the moment, but not all are suitable for me. I have expectations of a Cloud IDE.


#### Trial / Free tier /  Good pricing plan

I can spend my money on other things, I don't want to spend all my spare money on a Cloud IDE. It should have a *trial* - full version - to try it out. I don't like when the trial does not provide all features, because I can't really decide whether sign-up for a paid plan or evaluate another service.

It should have a *free tier plan* , so I could get a very minimal but 100% usable environment. I can live with 512MB memory and a very little disk space too. CPU is not important for me, I won't compile or mine bitcoin.

#### Encapsulated / Private Workspaces

Usually the free tier plans are available but don't allow you to protect your sensitive data. They're open to everyone. So a free tier should at least provide 1 private / encapsulated environment, so I can work on *non open-source projects*.

#### Terminal Emulator

I also expect a Linux environment with root access, so I can install a lot of things. It can be a Docker on anything else I don't really mind. It does not have to run 0-24. Enough if it's running when I'm working with it. If I can open a few ports and test my work that's also a good pro.

#### The IDE should be cool

In 2016 I expect a cool, customisable editor with awesome color schemes and themes. I don't like cloud editors with the look of the 90's.

### Cloud9 IDE

My first choice of Cloud IDE was the [Cloud9 IDE](https://c9.io). It has all the features I want.

I give them **9 / 10**. I'll explain why not **10 / 10**.

The IDE looks pretty awesome. Behind the scenes it's running [NW.js](http://nwjs.io/). If you're not using a Chromebook you could even download it and use it as your editor of choice. 

![Cloud9IDE pricing](/images/chromeos/cloud9_pricing.png)

The problem with their pricing is that the next step after the free is **$19** / mo. That is too much for such a service. I don't need unlimited private and public workspaces. I might only need a bit more disk or memory on my 1 private workspace, but I will never need more than let's say 2-3 workspaces.

I'd rather pay **$4 - $5** for 2-3 optional public/private workspaces instead. For now, the free tier plan is definitely enough for me. It works like charm. The free tier gives you **512MB** memory and **2GB** disk space. More than what you'll ever need in case if you're not using maven.

By default you can use it as one git repo per workspace, but I'd recommend not using that approach. I have around 30 repos checked out in one workspace and still have a lot of disk space.

![c9.io template](/images/chromeos/cloud9_template.png)

When you're creating a new workspace, you can choose a default template. It means your linux box will have a lot of specific things pre-installed and will spare you space, because you won't need to install them. Everything you install on your linux box will be counted too in your disk usage.

![cloud9ide](/images/chromeos/cloud91.png)

After creating the workspace it will boot up your linux box called container (docker) and put some default files on the disks and pop up the UI. I found it very convenient. You can highly customize the UI. Change the layout, but I think the default works the best. You have your file list on the left, edited files on the top/right and your terminal on bottom/right.

If you're a paid customer, you can even use SSH workspaces so you can use your own box as a workspace. Sometimes that would be useful, but since I'm on a free plan, I can SSH in, sync my files and do what I need to do.

![c9.io](/images/chromeos/cloud9ide.png)

Just to mention a few Cloud9 IDE features:

- Code Autocompletion
- Download and Upload Files
- File Revision History
- FTP Mounts
- Keybindings
- Language Analysis
- Multiple Cursors
- Search and Replace in Files
- Supported Languages
- Syntax Highlighting and Themes
- Themes
- Experimental Features

For more details, please visit [Cloud9 Docs](https://docs.c9.io/docs/)

### Summary

Most of the basic applications have web version which is pretty convenient and makes the switch easier. However if you're a hardcore Skype user, you'll experience degraded service compared to the Windows/Mac application. You won't be able to make voice/video calls, but you can write to your contacts and tell them that they can reach you via Google Hangouts. At least this is a good point.

- **HipChat**:  &#10003;
- **Slack**:   &#10003;
- **Twitter**:   &#10003;
- **Evernote**:   &#10003;
- **Google Hangouts**: &#10003;
- **IDE/Vim**:   &#10003;
- **Skype**:   &#10007;

### What comes next?

I'm evaluating 3 different Cloud IDE service at the moment and it worth to mention them. In the next blog post I'd love to cover those too. They seem to be competitive to Cloud9 IDE.

Meanwhile I bought another Chromebook because the [Acer C720P](http://www.acer.com/ac/en/US/content/series/c720) was too small. My current Chromebook is a [Toshiba Chromebook 2 - 2015 Edition (CB35-C3300) Full HD, Backlit Keyboard](https://www.amazon.com/gp/product/B015806LMM/ref=oh_aui_detailpage_o00_s00?ie=UTF8&psc=1) and I plan to write a review blog post about it.

What's more I'd love to compare the Acer to Toshiba to help you decide what to buy.

I also have a list of "What's not working on a Chromebook", and I'd love to share those with you. If you're not a DevOps, you might not need those applications or tools, but if you're a tech junkie, you probably need those and luckily I have workarounds too.

Stay tuned.

