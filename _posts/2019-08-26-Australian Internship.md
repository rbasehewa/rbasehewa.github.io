---
author: Ryan Maddumahewa
layout: post
title: "Australian Internship"
date: 2019-08-26 21:00
comments: true
category : PHP, Internships
tags:
- PHP, Internships
---

The Build Conference is now behind us where lots of exciting things were announced, among them the release of Visual Studio 2015 RC1. This blog post discusses the changes to the .NET framework, the solution layout / configuration and serves as an introduction to the recommended programming style encouraged by Microsoft going forwards. If you haven’t downloaded Visual Studio 2015, grab it now!

- #### FRAMEWORK CHANGES: 

Due to the rise of cloud hosting and the demand to host in any platform, not just Windows servers where you need to install the framework in order for your applications to work, ASP.NET 5 now supports two runtimes:

Full .NET: This is what was being shipped until now. It’s the version that gets installed on your machine.
CoreCLR: It’s the shiny new, cloud-optimized runtime that can run on any machine (Windows, Mac, Linux). To achieve this, the framework has been broken down into NuGet packages and applications only need to reference those packages that are needed. In fact only the primary dependencies, any inner dependencies are downloaded automatically. When you deploy your application to the host, it’s bundled up into a NuGet package itself including all the dependencies. This results in the bundle being larger than previously where only the files belonging to your application were included, but it means that the server doesn’t need to have the .NET framework installed.



Cheers,
Rangana
