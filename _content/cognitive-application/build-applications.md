---
title: Build
weight: 30
---
* Check to see if someone has already created a Personal Assistant application that you can reuse. Search for Expertise in the
* Explain how to build a Personal Assistant application.
* package expertise and models
* test

 Designing a Personal Assistant application is unlike other applications you have likely designed and built before.  There are more careful design considerations needed to create a engaging proactive personal user experience.  While you can use your normal design techniques like Design Thinking, there are some key point to make note of when building your application.  Here are practices that you should consider as you design your application so that it aligns with the Watson Assistant Builder programming model

1.  Organize the overall storyboard of the entire user experience for your application

2.  Break down the storyboard into distinct use cases.  Potential places to break down the use cases can be:
* time, date  -  Morning, evening,  during the week, weekend
* location - Where is the user in the journey.
* environment - In a car, in a house, in an office, in a conference room

3.  For each use case identify what interactions are being made
* User to device
* Device to device.
* What connecting technologies (like Bluetooth, or txt messaging or instant messaging)
* Device to user
* User to device

4.  Use the previous step to begin to identify what expertise you may require.  Check to see if the expertise already exists in the Watson Assistant Builder expertise repository.  What category of expertise is it?  Travel, health, entertainment, food, etc.

5.  From step three identify what type of Personal Assistant application you are trying to build.  There are specific design patterns and starters that align to the different types of Personal Assistant applications that you are building.

| Type                    | Devices          | Client Application         | Interaction                |
|:------------------------:|:----------------:|:--------------------------:|:---------------------------:|
| Personal Digital Assistant | Mobile         |  Native Mobile application |* voice   * text input      |


6. What environments or locations will scope the design for each use case.

	| Environments | Context  | What devices, connections and other information can provide context |
  |:----------------:|:------------------:|:-----------------------:|   
 	| Hotels, Home, Car, Office    				|  What context applies?
   Time or date, Location, Others |  What devices apply should be discovered?

 												                         * work phone
 												                         * home phone
 												                         * office phone
 								                                         * preferred method of communcation, messaging, location |
 	| 		Others?              | Others?                   |   Others?       |


 > **What next?** Learn how to [deploy your Personal Assistant application ]({{site.baseurl}}/cognitive-application/deploy-applications/) 
