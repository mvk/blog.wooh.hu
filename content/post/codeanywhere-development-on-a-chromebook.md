+++
date = "2016-06-28T10:36:04Z"
draft = false
title = "Codeanywhere - Development on a Chromebook"
description = "Codeanywhere - Development on a Chromebook"
tags		= [ "cloudIDE", "codeanywhere", "chromebook", "chromeos" ]
categories 	= [ "development", "DevOps" ]
image		= "cloudide/codeanywhere/codeanywhere_logotype.png"
+++

The biggest questions ever asked about Chromebooks: How can you use code on it, how can you run shell scripts and other things. Without enabling Developer mode, your best option is to use a Cloud IDE. Let me show you one. <!-- more -->

# Cloud IDE

Cloud IDE is a trendy thing nowadays. It’s especially useful for us - Chromebook users. We can’t have fancy IDEs like IntelliJ, Sublime, Vim, etc. We need to use online editors and online services to edit files, run commands on a linux box and so on.

You can of course use a the [Secure Shell](https://chrome.google.com/webstore/detail/secure-shell/pnhechapfaindjhompbnflcldabbghjo?hl=en) Chrome App as an altervative, but it does not support SSH key auth, and is pretty limited. I did not like it, because I don't want to use password auth, I did not find it secure enough.

There are actually four Cloud IDEs worth to mention at the moment:

- Cloud9 IDE - https://c9.io
- Codeanywhere - https://codeanywhere.com
- Koding.com - https://koding.com
- Codenvy - https://codenvy.com


I’m using Cloud9 IDE since I migrated to a Chromebook, so I wanted to try another one. Codeanywhere pinged me on Twitter okea week ago or so, and they actually forced me to try out their product. I had already registered an account, so I decided to use it for at least a week. 

{{< tweet 745702443904794624 >}}

# Pricing

A very important part is the pricing. Don’t get me wrong, I love to pay for good a good service, but I don’t like to pay for something I don’t need. This is why it is important for a company to have a good pricing strategy.

Codeanywhere has a free tier which includes the following features:

- Web editor
- Mobile editor
- SSH terminal
- Unlimited shares (1 active at a time)
- 1 revision
- 1 Remote Connection (FTP, VM, Cloud)
- 1 Container with 256 MB RAM, 2 GB HDD


It means I can use the Web UI from any notebook - including a Chromebook of course - and from mobile devices too. The web-based SSH or Terminal Console makes it possible to access any Secure Shell (SSH) servers through Codeanywhere, what’s more I can edit the files using the Codeanywhere Web Editor directly from any FTP, FTPS or SFTP based server.

Also I get an ubuntu/centos box with 256 MB memory / 2 GB disk space which is more than enough usually. Note that the container won’t run 0-24 (Always on), that feature is available only from the “Freelancer” plan.

So actually what I do is: I connect to my server using SSH and I’m editing the files there, so I don’t really need the Container provided by Codeanywhere at all. But just for sure the my development environment is also set up there, I just haven’t copied my secret keys yet. On demand I could do that.

# 3rd party tools / connections

I can use a lot of services via Codeanywhere:

![DO](/images/cloudide/codeanywhere/digitalocean.png)

- DigitalOcean - Codeanywhere is partnered up with [DO](https://www.digitalocean.com) so I can manage/connect to your droplets using Codeanywhere UI.
- Amazon S3 - I can edit files in a bucket. AWS credentials needed.
- Dropbox - I can edit files on DropBox
- OneDrive - A brand new thing: You can edit files in OneDrive
- GitHub - I can easily create a new Container based on a GitHub repository. It auto detects the file types in the repo and offers you to start a new container.
- BitBucket - I can easily create a new Container based on a GitHub repository. It auto detects the file types in the repo and offers you to start a new container.
- FTP/SFTP/SSH - As I mentioned before, you can edit files directly on any server.

When you use the Codeanywhere Container instead your own box, you’ll be given a specific hostname and ports 1024-9999 to check your service/website whatever you’re working on. Note that your container won’t run all the time while on a free plan.

The idea behind the “one container per project” is that the containers are cheap, easy to launch and you can separate your work from other things. I’m not a big fan of this setup, but sometimes it could be handy, but for now I don’t feel the need of it.

# Pros and Cons

So in general, I like Codeanywhere, but - just like any other software - it has bugs or annoying features. Let’s see  the pros and cons. Let’s start with the cons. Not all of them are real cons, rather incompleteness.

- Sometimes the SSH connection is doubled when I reconnect - reload my browser - and everything is doubled in the terminal. It’s not very frequent, but it happened a few times to me.
- There is no non-stop visible widget for disk / memory usage, the only way to check it, is run the `free` and `df` command. Compared to c9.io they have an always on top widget which shows the current CPU/Disk/Memory usage. This is something I’d love to see in Codeanywhere Web IDE too.
- Copy/Paste from/to a terminal is tricky from a ChromeOS and Windows. You need to use the CTRL + A, CTRL + C, and CTRL + A, CTRL + V to copy and paste. Which is pretty inconvenient to be quite honest. Other Cloud IDE providers can solve this problem.
- The terminal cursor is blinking and it annoys me pretty much.
- 2FA is only available from the “Freelancer” subscription - for $7 USD / month billed yearly / $10 billed monthly. 2FA should be available for everyone.
- The starter plan does not make sense. $2 USD / month for a support is so strange for me.
- No drag&drop to the file explorer, I need to right click on a folder and select upload. Two more click is annoying.
- Can’t define which Amazon region I want to use, so I usually ended up on us-east-1/us-west-1 instead of eu-central or so. (probably they don’t even have environments in EU)
- If the code is git versioned, I can’t see which line has changed or not just like in PyCharm/Vim/SublimeText.

Let’s see the pros:

- The service is cool as it is.
- Free subscription plan which allows you to do everything you need.
- The Web IDE is pretty trendy with customisable themes and colors.
- Upgrading to the “Freelancer” plan costs only $7 / month.
- I can edit the files on your server with the Web IDE, which is super cool!
- No need to use a Container, I can just use a remote connection.
- You can get a DigitalOcean coupon code!
- Can use S3, Dropbox, OneDrive, FTP, etc not only a server.
- Easy to sign-up and start your first Container. It takes about 30-45 sec.
- Actively developed, they release pretty frequently, community seems to be active.
- They’re pretty active on twitter.
- They answer to support tickets in 24hrs even for a free subscription.

# Summary

After about a week usage I’m still satisfied. Apart from the few annoying bugs like the copy and paste it really convenient and seems to be stable. During the 1 week period it was always reliable and available. I did not have any connectivity issues which is great.

All I had to do is copy the my codeanywhere public SSH key to my server and that’s all. I also added it to my GitHub repo, so I can checkout code.

For security reason, I’m not using the codeanywhere container for private repos, only for open source development. I use my own server for private projects. We all know how hard to secure a docker container, I don’t want to be surprised… :)

For me the free plan is absolutely enough but if you plan to use it heavily, you would need to sign up for the Freelancer plan, which isn't that much. Just do the math: 

A basic DigitalOcean droplet costs: **$5 / month + backup fee + VAT**, so it'll be around **$7**. For this price, you'll get:

- 20 GB SSD disk
- 512 MB memory
- 1000 GB data transfer

If you sign up to the **Freelancer** plan and use the containers provided by Codeanywhere you'll get:

- Everyhing included in the **Free** plan
- 1 Always On server, so actually you'll have a 0-24 running server.
- Premium support via E-mail
- Two-Factor Authentication
- 10 containers with 512 MB memory + 5 GB disk / each
- Unlimited shares and 50 active shares
- 50 remote connections (free plan includes 1 only)

Note that there is also a free trial option for the Freelancer plan. In overall you'll get a lot for just $7. It worth to subscribe to the Freelancer plan than using your own droplet at DigitalOcean with a Free plan at Codeanywhere.

To sum it up: Codeanywhere offers a pretty good service for all Chromebook users. Good job guys, keep up with the good work and I hope the items in the Cons section will be soon fixed/eliminated.


