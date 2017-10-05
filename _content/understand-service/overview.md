---
title: Overview
weight: 10
---
![Watson Personal Assistant Builder ]({{site.baseurl}}/images/wpa_overview.png)

## Your Application

Whatever type of application you are building, be it a mobile application, web application or some integrated hardware and software solution, requests from your users needs to be converted to text and sent to the Watson Personal Assistant Builder Core using the `converse` HTTP REST API.  At this point in time, the Builder service doesn't include Speech-to-Text conversion services, so this ability will have to be provided by your application services.  After sending the users' utterance to the core, it will receive a textual reply, along with JSON context data, for you to then show, or speak, the response to your user.

## The Builder Core

The Watson Personal Assistant Builder Core is the service you will interact with the most in the beginning.  The primary responsibility of the Builder Core is to route your users' utterance (in text form) to the "correct" Expertise that can handle the utterance.  Expertise are the main pieces of software you will create in order to provide a cognitive application.  Expertise use Natural Language Processing tools, like Watson Conversation Service, to determine the intent of your users' utterance and handle the request appropriately.  You'll learn what it takes to create Expertise in a later section.

## The Knowledge Store

The Watson Personal Assistant Knowledge Store service is used to store world objects and information about those objects.  The Expertise and Agents you develop will create and modify objects in the Knowledge Store using a NodeJS SDK.  Agents are another piece of software you will develop in order to give your cognitive application proactivity.

## The Agent Subscription service

The Watson Personal Assistant Agent Subscription service handles subscriptions to changes in the Knowledge Store objects and publishes notification events to Agents based on Rules you specify.  You'll create Rules using the Agent Subscription service NodeJS SDK.  You'll learn about Rules, along with Agents, in a later section.

>**What next?**  Learn about the [core]({{site.baseurl}}/understand-service/core)
