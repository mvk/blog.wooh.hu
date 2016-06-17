+++
date        = "2016-06-11T16:23:11Z"
draft       = false
title       = "Switching to Chromebook - Part I."
description = "Switching to Chromebook"
tags		= [ "google", "chrome", "chromebook", "chromeos" ]
categories 	= [ "gadgets" ]
image		= "chromeos/toshiba/toshiba_header_2.jpg"
+++

Let me share my story with you. This is a long one so I'll split it into a few small chunks so you won't get bored (hopefully). This is a story about how I changed my MacBook Pro to a Chromebook. <!--more--> I never thought it would be ever possible, but it was. And it's relatively easy and convenient.  You won't be able to use all your current applications on a Chromebook but there are pretty good alternatives and I'm 100% sure you'll like them too.

The first part covers information about me and about my work, what kind of apps I use, how I use them and what kind of notebooks I was using before.

### Emotionally attached to Apple

I'm a very long time Apple fan. I bought almost every gadget they made, except the iPhone. iPhone is an exception, because it's so much overpriced and the Google reference phones are way better and cheaper than the iPhones.


I bought my first iPod (Dock Connector) 20G around 2004, earphones, in-ear earphones, iBook G3, iBook G4 iMac G3, iMac G4, iMac intel, PowerBook G4, MacBook Pro, MacBook Air, iPod Shuffle... so I spent a lot of money buying these awesome gadgets. Luckily most of the MacBooks were paid by my actual employer. I loved them and still love them. All of my MacBook Pros are CTO setup, so all of them had extra memory + extra CPU + extra disk, because I thought I need it.

Apple gadgets are really cool. From UX perspective: they're all perfect. Well, almost perfect, but usually better than other things. The big con is usually their price. All of'em are overpriced. Yeah. Let's face the truth.

### I'm a DevOps Engineer

I spend most of my time (50%) using a terminal and 50% in a web browser. I was tracking this with RescueTime. For more than 2 years I'm not using any e-mail clients like "Mail", or "PostBox". I was a pretty huge PostBox fan too, but it used up 2-3G memory so I finally deleted it from my Mac.

So what I mostly need is a terminal and internet connection, sometimes with a VPN, and a browser. It's just a convenient fact, that I install a lot of console applications on my mac using brew or macports. So I can run a few things locally, but in the end everything will be executed on a server or on a JenkinsCI server. No real reason to run things locally. Git branching is pretty cheap and a jenkins job can be configured to run only my testing branch, so I can commit a lot of trash and wait jenkins for doing it's job.

Other applications I was running are:

- HipChat
- Slack
- Skype
- Evernote
- TweetDeck
- Sublime 2
- PyCharm
- Vim
- 1Password
- Yubico Authenticator
- etc...

In Part II. I'll tell you how can you use these applications or how can you switch to other similar applications so you won't feel yourself blocked.

Another cool MacBook feature is that if I close it, it goes to sleep. If I open it, it wakes up and I can continue my work where I left it off. This is the main reason why I love the Mac. Linux and *BSD were pretty bad at it and I gave it up after a while.

So let's be honest: using a Mac for a terminal and a web browser is a bit luxury. A MacBook Pro costs around $1,500 - $2,000 USD. You can get them a bit cheaper of course, but those aren't "powerful" enough.

![MacBook Pro/Air Bulldog Decal](/images/chromeos/macbookpro.jpg)

But yeah, a MacBook Pro/Air is pretty trendy and can stick cool decals on the back, looks great, made from awesome material and has a great smell for 1-2 month. But I think that's all. I don't think that the fact it's running [OS X](http://www.apple.com/osx/) would be listed in the pros column.

### Previous attempts

Before I was using Macs, I used custom built notebooks with NetBSD/OpenBSD as my operating system of choice. Those were pretty powerful machines at that time. 2x2.8Ghz CPU with HyperThreading technology. I loved it. After using iBooks for a few years I thought what if I can switch back and use *BSD or Linux on a notebook, so I bought a Toshiba. I tried everything but I wasn't able to "like" or "love" it, so finally I gave it to a friend. I bought another MacBook.

Somehow even a Toshiba notebook with a Linux/BSD wasn't able to impress me. I was disappointed but happy with my new MacBook.

### Why I decided to switch

About a month ago I read some news on [Hungarian Unix Portal](http://hup.hu) about Chromebooks. The news said that more chromebooks were sold in 2016 Q1-Q2 than MacBooks. This time I couldn't ignore this information.

4 years ago when I was in San Francisco, the Google Pixel had been just introduced. It was really horrible, everybody said that it's a completely useless laptop. So I started to ignore all news related to Chromebooks, until now.

### Experiment on a MacBook Pro

Before buying anything, I wanted to make sure that I can survive with only a Chrome browser on my Mac for more than a day. So I suddenly closed all my running apps on my Mac except a Google Chrome. I read a lot of articles about cloud editors and alternatives to local editors.

I also wanted to know how to use SSH from a browser. Another big question was the my password manager. The chrome extension for [1Password](https://1password.com/) is only a wrapper around the local application, so I finally ended up using LastPass which has a web version. 1Password also has a web version, but that costs way more than LastPass. So actually I'm evaluating both.

I found a few promising cloud IDEs. They mostly provide an ubuntu box too as a terminal. They're docker containers, I can install anything I need on them. They have free subscriptions but they're mostly enough for me. I only need 1 private workspace with a 2G disk and 512M memory. More than what I really need. I also have a personal server at [DigitalOcean](https://www.digitalocean.com) so if I need more disk space or capacity, I just used that server too.

### Experiment on a Chromebook

After about 7 days I was still using only a browser on my Mac so I thought it's a good idea to move ahead and find a cheap used Chromebook for a real ChomeOS experience.

Unfortunately in Hungary there are no Chromebooks at all, but luckily we have a local ebay like site which has a few used chromebooks listed. I was looking for a Chromebook with 4G memory. The 2G ones are a joke I guess. Finally I found one for **$198 USD**. It was the **Acer C720P Touch** Chromebook. It has a small screen but has HDMI to extend the screen to my monitor which could be definitely enough.

![Acer C720P](/images/chromeos/acer/acer_3.jpg)

> 11.6" HD Multi-Touch LCD  
> Intel Celeron CPU 2955U  
> 4GB DDR3 Low Voltage Memory  
> 16G SSD  
> HDMI  
> USB  
> SD CARD reader  
> Acer Nplify 802.11a/b/g/n - BT 4.0  
> Acer Crystal Eye HD Webcam  
> 3-cell Li-Polymer battery  

Such a good little laptop. The keyboard is a bit small, but I can still type on it. I'm a dvorak typists so the keyboard is important. If it's too small (like the EeePCs way back) I can't type on them.

### First-time User Experience (FTUE)

Although I bought it as a used laptop it wasn't used at all. It was brand new, it wasn't even unboxed, so I felt the excitement when I started to unbox it. I hadn't seen a non-apple laptop for a good amount of time.

After I unpacked it, I pressed the power button and wow! After about 4 seconds the login screen welcomed me. Holy cow! It's fast. Let's login. I had to select my country, select my keyboard layout (dvorak is supported by default) and select a wifi network. Without a wifi network you can't login for the very first time. Later you can, but for the very first time you need to be connected.

The next step is to enter your google username and password. My Google account is protected by a [Yubikey 4](https://www.yubico.com/products/yubikey-hardware/yubikey4/) which is a USB security key used as my 2FA of choice. On my Mac I even used it with [challenge response](https://www.yubico.com/wp-content/uploads/2016/02/Yubico_YubiKeyMacOSXLogin_en.pdf). After I entered my username and password it asked me to use my security key aka my yubikey. I just pressed it and voila! I was logged in. So note that your USB security key will work like charm on a Chromebook.

In a few seconds it synced down all my Chrome data from the cloud including my browsing history, bookmarks, chrome extensions and chrome applications like [Line Messenger](https://play.google.com/store/apps/details?id=jp.naver.line.android&hl=en). Pretty convenient!

By default ChromeOS won't ask a password when waking up from a sleep, so before starting any work on this machine I set this up. Unfortunately here isn't an option to enforce the presence of a security key (like yubikey), but I can live without it. The login is a pretty cheap operation so you can just logout instead of just lock your machine. All browser tabs will be reloaded after logging back and you can continue your work.

I opened up a Chrome and started to browse. Everything seemed smooth, fast response from the browser. So far so good! Attached my external monitor to the Chromebook without any issue. I attached my Logitech HD Webcam to it and it was able to use it too.

![Acer + External](/images/chromeos/acer/acer_external.jpg)

So far we only covered a few things, 3 out of 4 are working:

[&#10003;] Yubico 4 (Authentication)  
[&#10003;] Webcam  
[&#10003;] External monitor  
[&#10007;] 1Password

In [part 2](/post/switching-to-chromebook-part-2), I'm going to show you how to migrate your digital life to a Chromebook from your Mac and what problems you will encounter. I'm going to tell you what kind of cloud editors I started to use and what will work on your Chromebook and what won't.