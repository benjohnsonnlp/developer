---
title: Overview
weight: 10
---
![Watson Personal Assistant Builder ]({{site.baseurl}}/images/wpa_overview.png)

## Your Application

Whatever type of application you are building, be it a mobile application, web application or an integrated hardware and software solution, requests from your users need to be converted to text and sent to the Watson Personal Assistant Builder Core using the `converse` HTTP REST API.  In this beta, the Builder service doesn't include Speech-to-Text conversion services, so this ability will have to be provided by your application services.  After sending the users' utterance to the core, your application will receive a JSON reply that includes, along with JSON context data, the textual reply for you to then show, or speak to your user.

## The Builder Core

The Watson Personal Assistant Builder Core is the service you will interact with the most in the beginning.  The primary responsibility of the Builder Core is to route your users' utterance (in text form) to the "correct" Expertise that should handle it.  Expertise are the main pieces of software you will develop in order to produce a cognitive application.  Expertise use natural language processing tools, like Watson Conversation Service, to determine the intent of your users' utterance and handle the request appropriately.  The Core routes the utterance based on a confidence score returned by expertise relevant to the current information on the context.  You'll learn what it takes to create Expertise in a later section.

## The Knowledge Store

The Watson Personal Assistant Knowledge Store service is used to store world objects and information about those objects.  The Expertise you develop will create and modify objects in the Knowledge Store using a NodeJS SDK.  The Builder Core will also create and modify information in the Knowledge Store based on the context passed to the core from your application/solution.

## The Agent Subscription service

The Watson Personal Assistant Agent Subscription service handles subscriptions to changes in the Knowledge Store objects and publishes notification events to Agents.  Agents are the primary pieces of software you will develop in order to give your cognitive application proactivity.  You'll also create Rules, using the Agent Subscription service NodeJS SDK, to limit and focus the event notifications to Agents.  Agents can also create and modify objects on the Knowledge Store.  You'll learn about Rules, along with Agents, in a later section.

## Summary

You'll create, or reuse, Expertise to make your personal assistant intelligent.  You'll create Agents to act on changes in the Knowledge Store to proactively prompt or do things for your users.  You'll create Rules to limit when particular Agents act.  Expertise, Agents and Rules, together with information collected and maintained in the Knowledge Store, will give you a powerful and proactive personal assistant for your cognitive application. 

![Watson Personal Assistant Builder final]({{site.baseurl}}/images/wpa_overview2.png)

>**What next?**  Learn more about the [Builder Core APIs]({{site.baseurl}}/understand-service/core) 
