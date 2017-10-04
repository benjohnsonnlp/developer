---
title: Concepts
weight: 20
---

## Watson Personal Assistant Builder architecture
![Watson Personal Assistant Builder ]({{site.baseurl}}/images/markitecture.png)

## Natural language artifacts
The Watson Personal Assistant Builder uses the same natural language artifacts as the Watson services. To learn more, see the following references:

*  Utterance is a spoken word, statement, or vocal sound
*  See [Intents](https://www.ibm.com/watson/developercloud/doc/conversation/intents.html)
*  See [Entities](https://www.ibm.com/watson/developercloud/doc/conversation/entities.html)
*  See [Dialogs](https://www.ibm.com/watson/developercloud/doc/conversation/dialog-build.html)

## Client applications
A collection of user utterances or other types of interactions with a user are collated to create a client application.  Client applications often run on a device.  WPA Builder includes [client applications]({{site.baseurl}}/cognitive-application/client-application-integrations/) that you can readily reuse.

### Devices
A device is a mechanical and or electronic equipment that is designed for a specific purpose, such as:

* Communicating or interacting with other people or devices by voice, texting, presence, or other gestures
* Sensing surrounding conditions such as temperature, humidity, position, force (vibration, impact), sound, optical (light, video, photo), chemical, automotive or other measurement
 
Devices enable the client application to run.
Example devices include: mobile phones, computer laptops, smart speakers, or other sensors.

## Services
Services support the needs of the WPA Builder offering, applications, or expertise.   Services are available in IBM Bluemix Catalog. Bluemix is an open standards cloud-based development platform. 

[Watson](https://console.ng.bluemix.net/catalog/?category=watson) cognitive services are available for you to build applications and or expertise. [Watson services sample applications](https://github.com/watson-developer-cloud/).  

WPA Builder includes and utilizes some of Watson services, such as Speech-to-Text, Text-to-Speech, and Conversation services.    You can also create your services in [Bluemix](https://www.ibm.com/watson/developercloud/doc/common/index.html) to power your expertise.

### Voice service
The Voice service converts spoken user utterances into text. This text is sent to the WPA Builder service to process.   The Voice service waits for a text response from the WPA Builder service and converts it to speech.  The Voice service sends the voice response to the client application that initiated the interaction using the unique token ID. The default services in WPA Builder include Speech-to-Text and Text-to-Speech services used by the Voice service, but they can be replace with alternatives.  The Voice service authenticates and authorizes devices to interact with the WPA Builder service.  The Voice service maintains user sessions with the device and ensures that requests are responded to in a timely manner.  The Voice service is a WPA Builder service. Learn more about the Voice service [here]()  

### WPA Builder service
The Watson Personal Assistant (WPA) Builder service allows developers to quickly design, build, test, deploy, and run Personal Assistant applications such as personal assistants for their users.  The WPA Builder service provides the following set of capabilities that are accessible by developers programmatically via APIs.

* Registering expertise so that it can be discovered
* Routing requests to the right expertise
* Conversing with expertise
* Organizing expertise by group and organization
* Verifying the health of expertise

The Personal Assistant Builder service is a Watson Personal Assistant Builder service. Learn more about the Personal Assistant Builder service [here]()  

### Knowledge and Reasoning service
Watson Personal Assistant applications automate a task without requiring the user to ask for help.  Using the Knowledge and Reasoning service, any service, device or sensor can be used to anticipate a user's needs, understand the context of their activity, the space around them and suggest entertaining or helpful experiences.  The Knowledge and Reasoning service allows objects rules to invoke expertise proactively to address a user's needs.  The Knowledge and Reasoning service includes:

* Query API you can create, delete or query, or update Watson Personal Assistant objects.
* Rules API to determine when to trigger expertise based on state attribute changes.  

By default, IBM will provide a set of real world objects you can start with.  The Knowledge and Reasoning service is a Watson Personal Assistant Builder service.  Learn more about the [Knowledge and Reasoning service]({{site.baseurl}}/knowledge/proactive/) [here]()   

### Objects
An object is a data structure that represents an object or concept in the physical world.  A user can interact directly with an object or through a command and control using the Voice service, Knowledge and Reasoning service objects, Personal Assistant Builder service, and corresponding expertise that are registered with the Personal Assistant Builder service. Examples of object interactions include:

* A door sensor object whose door state is open or closed.
* A temperature sensor object whose temperature state is above or below 34 degrees.
* A todo list concept whose completion state is cancelled, done, or not started.

### Rules
An agent is client side code that can set an Object's state or subscribe to be notified when any object type's state changes.  Agents can be included in Expertise that have been registered in the Watson Personal Assistant Builder service, or sensors that have been integrated with the object or other services.

### Blackboard
The Blackboard is a concept that allows Knowledge and Reasoning services to make proactive applications and expertise using the Personal Assistant Builder service.  The Knowledge and Reasoning service includes the IBM Graph databases service.  The blackboard uses this service to represent a common shared data model that allows objects to make themselves discoverable within a space.  The Knowledge and Reasoning service includes a message queue service.  The blackboard uses this service to allow agents to publish and subscribe to object state changes. The blackboard is programmatically accessible by the Personal Assistant Builder service, objects, agents, and expertise that are registered with a Personal Assistant Builder service.

### Cognitive Profile service
The Cognitive Profile service enables expertise to be personal.  These capabilities will soon be accessible by developers programmatically through Rest APIs.  Learn more about the Cognitive Profile service [here (not yet available)]()  

## Expertise
An expertise is an atomic reusable program for a single domain that allows a customer to experience or automate a task in a more intuitive proactive, personal, and human way by using a device interaction like voice, texting, presence, or other gestures.  Expertise provide end user value without requiring data or expertise from other companies' services.  Expertise can be generic or specialized, such as “Order a pizza” vs “Order Domino’s Pizza”.  A user's personal preferences and information is only shared with the other expertise they use and with the data access permissions the user allows when using an application. Learn more about the expertise [here]()   

Watson Personal Assistant application developers can create new expertise or use existing expertise to fulfill a user's needs.  Applications built with the Watson Personal Assistant Builder can remember a user's journey in the physical and virtual world.  Learn more about the Personal Assistant Builder service [here]()   

## Application
An application assembles client applications, expertise, and Knowledge and Reasoning rules and objects that when instantiated enable a delightful personal experience within the context of an cognitive space by effortlessly connecting a user with the choices they have made. These choices include the expertise that are included in the application and that they add to their allow in their user journey. Applications built with the Watson Personal Assistant Builder can anticipate a user's needs and suggests actions before, during and after their user journey.  Both the application and the expertise remember's a users past experiences and data.  Expertise do not access other expertise user data directly. Watson Personal Assistant applications instead subscribe and reason about object in a space that then trigger registered expertise to active proactively. IBM has created the IBM Watson Hotel Spaces application using the Watson Personal Assistant Builder.

## Roles

### User
A user is who interacts with a Watson Personal Assistant application through a device, place, object or another person through the ConsumerIOT Solution.  Here are some example user interactions:

* Utterances, words that a person speaks to the device
* Gestures or physical movement that a device observes by touching or touch less like Like swiping
* Positional movement  with respect to a device
* Manual text input like texting

### An expertise developer role
The expertise developer typically performs the following tasks:

* Designs, develops and tests expertise using Watson Personal Assistant Builder service.
* Identifies what objects and state changes can make his expertise proactive in the Knowledge and Reasoning service
* Creates the agents to react to Blackboard Object state changes.
* Registers his expertise with a Watson Personal Assistant Builder service

### An application developer role
The application developer typically performs the following tasks:
*

### IT administrator
Adminstrates users, applications, expertise, services and devices. He also monitors applications and expertise availability and log files for problems.

## Interaction patterns
User ->  Device/Object -> Device/Object Gateway -> Voice service -> Personal Assistant Builder service -> Watson services -> expertise services

### An example interaction sequence ( without proactiveness )
1. User -> Speaks the words “unlock the conference room door”
2. Device - Sends the utterance to the Voice service that converts utterance from speech to text using the Watson Speech to text service.
3. Voice service -> Sends utterance text to Personal Assistant Builder service to determines Intent.
4. Personal Assistant Builder service -  Using the token id determines the user, context and required expertise needed to resolve the request. Depending on the need will send additional contextual information and enriched utterance text
5. Watson service ->  Watson Conversation service determines the users intent and if it can respond with an answer or other action to resolve the request.  The actions may invoking other expertise. In cases where it can’t it may request more information from the user.  It sends the text and status back.
6. Personal Assistant Builder service -  Collects all the responses from all the expertise.  This may include responses from other expertise to achieve a solution to the user’s task to unlock the door.   Sends response utterance text to the smart speaker or client application.  Sends action to unlock the door to the internet connected lock in the door.
7.  Voice service - Converts the text response to speech wav file that is sent to the user.
8.  User or Object - User receives a response that the door is being unlocked and the door receives the unlock signal from the expertise.

### An example interaction sequence ( with proactiveness )
To be added.

**What next?** [Learn how to create your first expertise]({{site.baseurl}}/expertise/what-are-they/)

--------
Help and [contribute]({{site.baseurl}}/contribute/contribute-doc/)
