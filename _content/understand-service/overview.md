---
title: Overview
weight: 10
---
![Watson Assistant Components]({{site.baseurl}}/images/wpa_overview.png)


## Conversation 

In the beginning, you'll interact with the Conversation component the most.  The primary responsibility of the Conversation component is to route your users' utterance (in text form) to the "correct" Expertise that should handle it.  Expertise are the main pieces of software you will develop in order to produce a cognitive application.  Expertise use natural language processing tools, like Watson Conversation Service, to determine the intent of your users' utterance and handle the request appropriately.  The Conversation component routes the utterance based on a confidence score returned by each expertise and information on the context.  The next page will give you an overview of the Conversation component APIs you'll use to register your expertise and you'll learn what it takes to create Expertise in a later section.

## Knowledge 

The Knowledge component is used to store world objects and information about those objects.  The Expertise you develop will create and modify objects in the Knowledge component using the REST API or a NodeJS SDK.  The Conversation component will also create and modify information in the Knowledge component based on the context passed to the Conversation component from your application/solution.  A later page will give you an overview of the Knowledge component REST APIs and you'll get a hands-on tutorial using the NodeJS SDK in a later section. 

## Reasoning 

The Reasoning component handles subscriptions to changes in the objects and relations in the Knowledge component and publishes notification events to Agents.  Agents are the primary pieces of software you will develop to give your cognitive application proactivity.  You'll also create Rules, using the Reasoning NodeJS SDK or REST API, to limit and focus the change event notifications to your Agents.  Agents can also create and modify objects in the Knowledge component.  A later page will give you an overview of the Reasoning APIs and you'll learn how to create Rules and Agents using the NodeJS SDK in a tutorial.

## Your Application

Whatever type of application you are building, be it a mobile application, web application or an integrated hardware and software solution, requests from your users need to be converted into text and sent to the Conversation component using the `converse` REST API.  In this beta, Watson Assistant doesn't include Speech-to-Text conversion services, so this ability will have to be provided by your application services.  After sending the users' utterance to Conversation component, your application will receive a JSON reply that includes, along with JSON context data, the textual reply for you to then show, or speak to your user.

## Summary

You'll create, or reuse, Expertise to make your application intelligent.  You'll create Agents to act on changes in the Knowledge component to proactively prompt or do things for your users.  You'll create Rules to limit when particular Agents act.  Expertise, Agents and Rules, together with information collected and maintained in the Knowledge component, will give you a powerful and proactive assistant for your cognitive application. 

![Watson Assistant Based Application]({{site.baseurl}}/images/wpa_overview2.png)

>**What next?**  Learn more about the [Builder Core APIs]({{site.baseurl}}/understand-service/core) 
