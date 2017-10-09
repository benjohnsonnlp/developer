---
title: Services
weight: 30
---
Here are the available cognitive services and links to the API reference documentation.  When using Swagger in the browser and clicking the "Try It Out" button, make sure you have pasted your API key in the text input field at the top of the page near the Explore button.  You will get an unauthorized error if you don't provide your API key in this field.  

### Watson Assistant Builder services

* [Assistant Builder Service]({{site.baseurl}}/broken_link)
* [Knowledge and Reasoning Objects]({{site.baseurl}}/broken_link)
* [Knowledge and Reasoning Subscriptions]({{site.baseurl}}/broken_link)

### Watson Assistant Builder service

## APIs
The Watson Assistant Builder service supports the following groups of API's:

Group | Description
--- | ---
Avatar | Avatar CRUD and expertise binding
Converse | Conversation with avatars
Expertise | expertise query
Expertise Registry | Registry for expertise which can be used by avatars (binding)
General | General information, health check etc.
Links | Avatar - expertise bindings query

## Avatar
Avatar is a virtual instance which combines set of expertise and is responsible
to find the best expertise in his set that can respond to a user request.
If expertise name is not specified, the avatar will find the best expertise to
respond based on decision algorithm which is based on context, confidence and
more.
The Sagan Core hosts avatars and enabled the applications to send user request
to an avatar using the REST API. The application should create an avatar, add expertise
and bind them to avatars before starting conversation with it.

Method | API | Description
--- | --- | ---
GET | /avatars | Get all created avatars
PUT | /avatar | Create new avatar
DELETE | /avatar/{avatarName} | Delete and remove an avatar
GET | /avatar/{avatarName} | Returns avatar data
GET | /avatar/{avatarName}/expertise | Returns all expertise bound to the avatar
PUT | /avatar/{avatarName}/expertise | Bind expertise to an avatar
DELETE | /avatar/{avatarName}/expertise/{expertiseName} | Unbind expertise from avatar

## Converse

Method | API | Description
--- | --- | ---
POST | /avatar | Converse
POST | /avatar/{avatarName} | Converse with specified avatar
POST | /avatar/{avatarName}/{expertiseName}/converse | Converse with avatar expertise

## Expertise

Method | API | Description
--- | --- | ---
GET | GET /expertise/{expertiseName}/avatars | Returns all avatars bound to this expertise

## Expertise Registry

The Expertise Registry is used as the place to register expertise that can be used by the core avatars. Avatars can only bind expertise which are registered in this registry.
If an expertise is deleted from the registry, the expertise will also be removed from all avatars which uses it.

Method | API | Description
--- | --- | ---
GET | /registry/organizations | Get all available organizations

## General

Method | API | Description
--- | --- | ---
GET | /configuration | Current core configuration
GET | /healthcheck | Sagan core server health check

## Links

Method | API | Description
--- | --- | ---
GET | /links | Get all existing bindings (avatar / expertise links)


## Other IBM services for powering expertise

* [Watson Services](https://www.ibm.com/watson/developercloud/)
* [Bluemix Services](https://console.ng.bluemix.net/apidocs)

* Knowledge Kits
  * [Food service](http://knowledge-kits.blekko.com/docs/api)
  * [Travel service](http://knowledge-kits.blekko.com/docs/api)
  * [How To service](http://knowledge-kits.blekko.com/docs/api)

## From the community and third party
Work is underway to support:

* IFTTT
* TripAdvisor
* Other third parties coming soon.

> **What next?** [Learn how devices interact with your Assistant application]({{site.baseurl}}/cognitive-devices/what-are-they/)
