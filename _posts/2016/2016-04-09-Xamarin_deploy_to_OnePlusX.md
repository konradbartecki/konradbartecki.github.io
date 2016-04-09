---
layout: post
title:  'Xamarin: Deploying to OnePlus X'
date:   2016-04-09
categories: xamarin android
tags:
  - xamarin
  - android
  - opx
  - oneplus
---
Xamarin simply does not like my One Plus X.
Everytime I build my Xamarin.Android app, it does build successfully then it looks like it is about to run on my phone and seconds later Visual Studio immediately exits debug mode. Nothing happens.
There's one workaround I've discovered. __You have to change the application package name. Every build.__
In Visual Studio go to your Android project properties and change the __Package Name__ to something different that it was a build before.
![VS Screenshot](http://i.imgur.com/k01xJhV.png)
