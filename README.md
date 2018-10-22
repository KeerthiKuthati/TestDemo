# Business solutions using Kaizala
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://docs.microsoft.com/en-us/kaizala/partnerdocs/customerticketingsolution)
 [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/KeerthiKuthati/TestDemo/pulls)
 
Most businesses want to focus their IT resources to help with core functions, while in reality a large chunk of their resources goes into deployment, maintenance, and driving adoption of the custom apps that are built-in house for line of business operations.

Kaizala provides an extensible platform that enables you to build custom Action cards for commonly-used tasks for organization which will show up in the Kaizala Actions palette like the [out-of-the-box cards](https://docs.microsoft.com/en-us/kaizala/actions/readme)

There are 2 ways you could create a custom action:
* Customizing templates present in [Kaizala management portal](https://Manage.kaiza.la.com) 
* Build / code a custom action

This repository aims at providing ready to use, diverse set of business solutions using custom action cards. Solution listed here are motivated by real life scenario and introduces capabilities of Kaizala action cards. Each solution includes action package and, or flow package and documentation

## Action package
Kaizala platform provides developer an action package SDK (called KASClient.js) – which is a javascript library that abstracts out platform specific functionality and provides a way to interact with the underlying Kaizala runtime. The developer could build a custom action in HTML / JS / CSS by calling into the SDK. A custom action is a zipped bundle of few HTML/JS/CSS files, manifest files and KASClient.js – the action package SDK

## Business solutions
Solution
Solution description
Action Package
FLow Package
Documentation
----| -------- |---|----|---
Display Industry Updates on kaizala|Send Industry trends to Kaizala from RSS Channels | Action package.zip Link|Flow Package.zip Link |[Documentation](https://github.com/KeerthiKuthati/TestDemo/blob/master/RSSFeedupdates.md)
Send Internal Periodic Alerts|Send corporate Event Alerts to Kaizala from SharePoint Lists |Action Package.zip Link| None| Documentation
Send Internal News|Send the corporate communication to Kaizala from SharePoint News Center|---|----| Documentation
Real time incident management| Raise IT help desk tickets & track status in Public groups
Access Business metrics on the go|Visualize real time sales funnel data 
Collect Sales order data from feet on street| Order taking card for feet on street from retailers


*Note*: For all the solutions KAS client is mandatory to be included as part of Action package. 

[Download latest version of KAS client](https://github.com/MicrosoftDocs/kaizala-docs/tree/master/Articles/Actions/KASClient) 

## Contributions [![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/KeerthiKuthati/TestDemo/pulls)

When contributing to this repository, please first discuss the change you wish to make via issue with the owners of this repository before making a change. 
* To fix a bug, fork the repo, Fix everything and create a pull request
* To upload a new business solution or modify the existing solutions with new variations,  Fork the repo, Make the necessary changes and create a pull request
* For typos, please do not create a pull request. Instead, declare them in issues with the right label.

Please note we have a code of conduct, please follow it in all your interactions with the project.

## Pull Request Process
Please consider the following criterions in order to help us in a better way:
* The pull request is mainly expected to be a code script suggestion, improvement or a new business solution
* A pull request related to non-code-script sections is expected to make a significant difference in the documentation. Otherwise, it is expected to be announced in the issues section.

## Issues
* If something is broken, File a [bug](https://github.com/KeerthiKuthati/TestDemo/labels/bug)
* If you want to try testing,  Look through [requests for test](https://github.com/KeerthiKuthati/TestDemo/labels/Testing%20required) and start testing
* Look through [open issues](https://github.com/KeerthiKuthati/TestDemo/issues) and see if there's a topic  you happen to have experience with. And then, preferably, share that experience with others.
* Find issues that [need wiki](https://github.com/KeerthiKuthati/TestDemo/labels/NeedWiki) entries and add the relevant info to the [wiki](https://github.com/KeerthiKuthati/TestDemo/wiki)
