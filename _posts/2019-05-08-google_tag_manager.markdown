---
layout: post
title:      "Google Tag Manager"
date:       2019-05-08 17:32:20 +0000
permalink:  google_tag_manager
---


> Google Tag Manager is a tag management system that allows you to easily manage and update tracking codes and realted code fragments on your website or mobile app -GTM

Once you add a segment of Tag Manager code to your project, you are able to deploy analytics and configure tag management from a web-based user interface. You can use Tag Manager's UI to set up tracking tags, establish triggers that cause your tag to fire when certain events occur and even create variables that can be used to simplify or automate your tag. 

When using Tag Manager, none of your tag code needs to live in the code base of your project, it all stays on the Tag Manager site. This can replace manually-coded tags from Google Ads, Google Analytics or other 3rd party tags. You can also create custom tags. 

You can use Workspaces to group and manage tag changes. Workspaces allow you to create multiple changes to your container (where all your tags for a project live). Team members can work on changes in different workspaces to keep from overwriting each others work and workspaces help with version control by giving you the opportunity to revert back to a previous version if needed. If a new version is created, each workspace will display a notification that the workspace is out of date and should be updated. 

Tags are segments of code provided by analytics, marketing, and support vendors to help you integrate products into your website or app. GTM comes with many supported tags, all of these options come with a pre-built template that you just need to fill in with the information you ask for. If you need to implement a tag that is not supported by Tag Manager, you can use a custom image or HTML tag. When creating a custom HTML tag, you can insert dynamic content by using variables. To create a variable just wrap it in double braces {{my_variable}}. 

Under the Advance Settings of a tag, you can set prioritization of when a tag fires. You can set it to a positive or negative number, higher numbers will fire before lower numbers. You can also enable a custom firing schedule so that a tag will fire during a specified timeframe. 

You can also set how often a tag fires, whether it is unlimited (whenever a trigger tells it to), once per event or once per page.

Tags fire in response to events and triggers are what listen to these events like for submissions, button clicks, or page views. Every tag must have at least one trigger in order to fire. 




