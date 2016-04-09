---
layout: post
title:  "Azure - How to deploy from secured external repository"
date:   2016-04-09 14:00:00
categories: azure
tags:
  - azure
  - deploy
  - ci
---
I had a problem recently, when I wanted to deploy my azure website automatically from external git repository hosted on Visual Studio Online. Once I've picked the Visual Studio Team Services option - it showed me only projects from my worksplace VSTS, but I wanted to deploy from my personal VSTS.


There are currently two options to workaround this.
Use old Azure portal at manage.windowsazure.com or embed your login and password into repository URL


If you want to use the second option here's how you should do it.
Take a note that if your login is an email - you should use an escape characters "%40" instead of "@" symbol,
so instead of using yourlogin@outlook.com you have to use yourlogin%40outlook.com

```
https://yourlogin%40outlook.com:password@yourHostedVSTS.visualstudio.com/DefaultCollection/YourProjectName/
```
