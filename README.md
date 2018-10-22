# Business solutions using Kaizala
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://docs.microsoft.com/en-us/kaizala/partnerdocs/customerticketingsolution)

Kaizala platform allows you to extend the client side functionality through custom actions (or cards). While all businesses want to focus their IT resources to help with core functions, the reality is that a large chunk of resources goes into deployment, maintenance, and driving adoption of the custom apps that are built-in house for line of business operations.

Kaizala provides an extensible platform that enables you to build custom Action cards for commonly-used tasks for organization which will show up in the Kaizala Actions palette like the out-of-the-box cards.

There are 2 ways you could create a custom action:
* Customizing templates present in [Kaizala management portal](https://Manage.kaiza.la.com) 
* Build / code a custom action

This repository provide ready to use, diverse set of business solutions using custom action cards. Solution listed here are motivated by real life scenario and introduces capabilities of Kaizala action cards. Each solution includes action package and, or flow package and documentation

# what is an action package?
Kaizala platform provides developer an action package SDK (called KASClient.js) – which is a javascript library that abstracts out platform specific functionality and provides a way to interact with the underlying Kaizala runtime. The developer could build a custom action in HTML / JS / CSS by calling into the SDK. A custom action is a zipped bundle of few HTML/JS/CSS files, manifest files and KASClient.js – the action package SDK

Solutions
Action Package
FLow Package
Documentation
------------ | ------------- |-------|---------
RSS Feed updates to work groups | Action package.Zip Link|Flow Package.Zip Link |[Documentation](https://github.com/KeerthiKuthati/TestDemo/blob/master/RSSFeedupdates.md)
Employee to Employee digital recognition |Action Package.zip Link| None| Documentation
Intenal news center|
Quote of the day|

Note: For all the solutions KAS client is mandatory to be included as part of Action package. 
* [Download latest version of KAS client](https://github.com/MicrosoftDocs/kaizala-docs/tree/master/Articles/Actions/KASClient) 

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
