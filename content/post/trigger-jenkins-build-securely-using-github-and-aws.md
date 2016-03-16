+++
date 		= "2016-03-16T09:05:26+01:00"
draft 		= false
title 		= "Trigger Jenkins Build Securely Using GitHub and AWS"
description = "The proper way to trigger a secured jenkins via a GitHub push"
tags		= [ "jenkins", "github", "amazon", "security" ]
categories 	= [ "jenkins", "work" ]
image		= "jenkins-github-aws/Breaking-Builds-Say-My-Name.jpg"
+++

### Because security does matter

I can say that I've seen thousands of [Jenkins](http://beta.jenkinci.io) masters. The non enterprise ones are usually triggering the builds via [GitHub](https://www.github.com) webhooks. You can do this via the [GitHub Plugin](https://wiki.jenkins-ci.org/display/JENKINS/GitHub+Plugin). It's mandatory to allow github to reach your jenkins master if you want to use this method. But there is a trade-off. Security vs. comfy webhooks...

The enterprise masters are mostly using SCM polling instead, because their jenkins masters are not available from the external network. GitHub can't reach their master. This is a show stopper, if you want to trigger a build immediately after a `git push`. 

Although using frequent SCM polling on hundreds of repos will cause huge I/O and CPU overload on your jenkins masters, so this blog post is mostly for Enterprise Jenkins customers and for the ones who want to secure and lock down their jenkins.

### The proper way

Luckily there is a plugin out there for a long time, but for some reason it remained unnoticed until now. The anonym plugin statistic says there is around only **457** installations for this plugin. How come? What is this plugin?

This mighty plugin is called the **GitHub SQS Plugin**

> This plugin integrates Jenkins with Github projects via Amazon's Simple Queue Service.
> 
> 1.   Consumes a message from an SQS Queue and triggers any jobs that have a matching github repository configuration.
> 2.   Automatically adds and removes the Github SQS Service hooks.
> 3.   Trigger build job using GitHub Amazon SNS service hook that use a SQS topic subscription.

Ohh, but this is super cool. Jenkins is simply polling an `Amazon SQS` queue. This does not cause I/O at all. If there is a `git push`, GitHub sends the payload using `Amazon SNS`, and the payload finally ends up in the `Amazon SQS`. Jenkins just grabs the payload and triggers any jobs that have a matching github repository configuration.

### Setup

The requirements are the following:

- Amazon Web Services subscription
- GitHub repository or repositories
- Jenkins

### Amazon SQS configuration

1. As a first step, login to your AWS console, select SQS service and create a new queue.

	![SQS](/images/jenkins-github-aws/create_sqs_1.jpg  "Create New Queue")

2. Enter the queue name. Let's call it `jenkins`. Click on `Create Queue`
	
	![SQS](/images/jenkins-github-aws/create_sqs_2.jpg  "Enter Queue Name")

3. Select the newly created SQS queue and record the `ARN`. You'll need it later.

	![SQS](/images/jenkins-github-aws/create_sqs_3.jpg  "SQS Summary")

### Amazon SNS configuration

1. Select SNS service in the AWS console and create a new topic.

	![SNS](/images/jenkins-github-aws/create_sns_1.jpg  "Create New Topic")

2. Enter the topic name. Let's call it `jenkins`.

	![SNS](/images/jenkins-github-aws/create_sns_2.jpg  "Enter Topic Name")

3. Select the newly created SNS topic and record the `ARN`. You'll need it later.

	![SNS](/images/jenkins-github-aws/create_sns_3.jpg  "SNS Summary")

### Amazon IAM configuration

It's time to create an `AWS Access Key ID` and  `Secret Access Key` for your jenkins and GitHub service. Select the `IAM` service and create a new user. By default generate an access key. Let's call this user `jenkins` too. Record the credentials.

	AWS_ACCESS_KEY_ID=AKIA...
	AWS_SECRET_ACCESS_KEY=Aq9x...


Attach a right `SQS/SNS` managed IAM policy to this newly created user.

As a best practice, you should restrict the policy to have access only to the previously created `SQS/SNS` resources. You can read more about [Amazon IAM policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage.html)

The Amazon Web Services configuration is now complete.

### GitHub configuration

In case if your jenkins master has the rights to manage webhooks on GitHub, you can skip the next SQS configuration section. I usually don't allow my jenkins to manage github hooks, because that requires administrative rights on a specific repo or even in the organisation.

### GitHub webhook SQS configuration

1. Select your repository and select the `Settings` tab.

2. Select `Webhooks & services`.

3. Select `Add service` from the dropdown menu and select `Amazon SQS`.

	![SQS](/images/jenkins-github-aws/github_1_sqs.jpg  "SQS github")

4. Enter the AWS credentials and the `ARN` for `SQS` and save it.

	![SQS](/images/jenkins-github-aws/github_2_sqs.jpg  "SQS github")

### GitHub webhook SNS configuration

1. Select your repository and select the `Settings` tab.

2. Select `Webhooks & services`.

3. Select `Add service` from the dropdown menu and select `Amazon SNS`.

	![SQS](/images/jenkins-github-aws/github_1_sns.jpg  "SNS github")

4. Enter the AWS credentials, `region`, and the `ARN` for `SNS` and save it.

	![SQS](/images/jenkins-github-aws/github_2_sns.jpg  "SNS github")

The GitHub configuration is now complete.

### Jenkins general configuration

1. Install `GitHub SQS Plugin` via the plugin manager and restart your jenkins.

2. Go to your jenkins's configuration page `https://yourdomain/configure` and locate the `Amazon SQS Configuration` section.

3. Enter the AWS credentials and the SQS queue name or URL. Hit `Test Access` to verify it's working.

4. Select `Manually manage GitHub SQS hook` if your jenkins does not have access to manage webhooks on GitHub.

	![jenkins](/images/jenkins-github-aws/jenkins_1.jpg  "Jenkins SQS")


### Jenkins job configuration

Go to your job's configuration page and locate the `Build Triggers` section. Enable the `Build when a message is published to an SQS Queue` option and hit `Save` or `Apply`.

![jenkins](/images/jenkins-github-aws/jenkins_2.jpg  "Jenkins SQS")


### Profit

We're all set. Your jenkins job is configured and will be triggered when somebody pushes a code to the repository. It clean and safe.

### References

- [Jenkins](http://beta.jenkins.io)
- [GitHub SQS Plugin](https://wiki.jenkins-ci.org/display/JENKINS/GitHub+SQS+Plugin)
- [AWS IAM](http://docs.aws.amazon.com/IAM/latest/UserGuide/introduction.html)
- [AWS SQS](https://aws.amazon.com/sqs/)
- [AWS SNS](https://aws.amazon.com/sns/)
- [GitHub](https://github.com/)
