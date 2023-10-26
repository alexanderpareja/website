+++
title = 'Deploying on Amplify'
date = 2023-10-26T02:32:28-04:00
draft = false
+++

![](/images/vampt_deployonaws.jpg)

[![Built with Hugo](https://img.shields.io/badge/Built%20with-Hugo-%23FF4088)](https://gohugo.io/)

[![Deployed with AWS Amplify](https://img.shields.io/badge/Deployed%20with-AWS%20Amplify-%2300AADD)](https://aws.amazon.com/amplify/)

# Deploying This Site on AWS

My journey and the challenges I faced while deploying my blog using the Hugo framework on AWS Amplify.

## The DNS Resolution

While the process seemed straightforward initially, I ran into an unexpected issue: the CNAME records wouldn't resolve. For those unfamiliar, CNAME records are for mapping custom domains to the provided AWS URL. I anxiously waited, tested, and retried, but it appeared stagnant. 

Patience proved to be the remedy. Approximately 24 hours later, the domain started functioning as intended. This was a reminder that DNS resolutions aren't always instantaneous and sometimes require a longer waiting period.

## The Blank Screen

After overcoming the DNS resolution issue, a new problem presented itself. Upon visiting the provided AWS URL, all I was greeted with was a blank screen. No error messages, no content, just emptiness.

After some investigation, I found the problem in the Hugo configuration file. The `baseUrl` parameter was pointing towards my custom URL, which at the time, had unresolved DNS records. By switching the `baseUrl` to the AWS assigned URL temporarily, the site started deploying correctly.

## Wrapping It Up

After ensuring the site was deploying as intended, I waited for the DNS resolution to complete fully. Once it did, I switched the `baseUrl` back to my custom domain. 

A couple of valuable lessons in patience and the importance of double-checking configuration files.

