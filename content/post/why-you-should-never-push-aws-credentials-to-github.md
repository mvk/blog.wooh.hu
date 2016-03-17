+++
date = "2016-03-17T08:56:23+01:00"
draft = false
title = "Why You Should Never Push Your AWS Credentials to GitHub"
description = "Why You Should Never Push AWS Credentials to GitHub"
tags		= [ "aws", "ec2", "api", "security", "github" ]
categories 	= [ "amazon", "security", "github" ]
image		= "aws-exposed/cyber-security.jpg"
+++

This is a story of a friend of mine who has a strange hobby: He loves `nodejs` and other javascript related frameworks. A few days ago unfortunately I sent him a [link](http://claudiajs.com) about `Claudia.js`. Which is actually a cool thing by [Gojko Adzic](https://gojko.net/).

> Deploy Node.js microservices to AWS easily

He was so excited. He never used Amazon Web Services before so he signed up for an [AWS Free Tier](https://aws.amazon.com/free/). He found a few tutorials, and he just followed the steps in the tutorial.

{{<vimeo 156232471>}}


### The Email You NEVER Want to Get

Tree days later on a sunny morning, he asked me if there is anything to do with `AWS credentials`. He got an e-mail from AWS to remove his AWS credentials. He was pretty calm, had no idea that this is something pretty serious.

Hmm, that sounded pretty bad, so I asked him to forward the e-mail to me. Actually it was THE email you never want to get.

> Amazon Web Services has opened case xxxxxx on your behalf.
>
> The details of the case are as follows:
> 
> Case ID: xxxxxx  
> Subject: Your AWS account is compromised  
> Severity: Low  
> Correspondence: Dear AWS Customer,  
> 
> Your AWS Account is compromised! Please review the following notice and take >immediate action to secure your account.
>
> Your security is important to us. We have become aware that the AWS Access Key AKIAXXXX (belonging to IAM user "xxx") along with the corresponding Secret Key is publicly available online at github.

![github commit](/images/aws-exposed/commit.jpg  "GitHub Commit")

Holy shit. It seems he had accidentally committed his AWS keys to GitHub. At this point I made a phone call and asked him to quickly review his AWS account. He logged in and saw 20 running instances instead of his t2.micro. His account was full of `g2.8xlarge` instance types. That's not that cheap.

![nano](/images/aws-exposed/nano.jpg  "Nano")


So I asked him to immediately deactivate all AWS API keys and terminate all instances in his current region and asked him to check all regions too. Unfortunately it wasn't enough. Replacement servers were fired up after a few minutes. I knew that it won't be that simple, so I felt I have to do it myself.

I logged in with this root AWS credentials and navigated to the `Auto Scaling Groups`, but that was empty. My next tip was `Spot Request` instances. Bingo. There were **20** spot requests / region with `$3.2` max price.

![spot bids](/images/aws-exposed/spot-requests.jpg  "Spot Bids")

"Luckily" his instance and spot limit were around 20, so I cancelled all spot bids and terminated all servers too. Double checked all regions.

### The worst part

As the account was cleaned up, it was time to check the billing. His account was exposed for about 2-3 days, which can cause a lot of instance hours. I clicked on the `Billing & Cost Management` tab and saw the following on the dashboard:

![billing](/images/aws-exposed/billing.jpg  "Billing")

> Current balance is **$6,437**

Oh my. I wasn't quite sure how to tell him. I was shocked. I asked my colleague about this, and he told me that:

> AWS will probably credit him back if he gets it closed up quickly

I hope this is the case and he won't need to pay that.

### Takeaway

Can't emphasize enough how important is to keep your credentials safe. What can you do to prevent this happening from the future?

1. Use ephemeral tokens if possible. This is provided by [AWS Security Token Service](http://docs.aws.amazon.com/STS/latest/APIReference/API_AssumeRole.html). You can define temporary cedentials with it.

	> The temporary security credentials are valid for the duration that you specified when calling AssumeRole, which can be from 900 seconds (15 minutes) to a maximum of 3600 seconds (1 hour). The default is 1 hour.

2. [Monitor Estimated Charges Using Billing Alerts](https://aws.amazon.com/blogs/aws/monitor-estimated-costs-using-amazon-cloudwatch-billing-metrics-and-alarms/) on a daily basis. There are tools out there already. 

3. Remove keys after using them. If you're done with experimenting, do not leave the keys there. Just remove them.

5. Decrease your default limits. If you know you won't need ~20 instances only 1-2, open a support ticket and ask them to decrease your instance limits.

6. Use IAM roles and policies. Restrict the accesses of the keys to as minimum as you can. A few examples are [here](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_examples.html).

7. Do not store your credentials on github without encrpyting them.
