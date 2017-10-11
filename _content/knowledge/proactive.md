// remove this line to include this page in the sidebar
---
title: Understand and design for proactiveness
weight: 19
---
## Knowledge and Reasoning Service
Expertise can proactively engage the user when certain conditions are met. This capability is provided programmatically by the Knowledge and Reasoning service.  The Knowledge and reasoning service provides:
  * A shared data object storage service to store object models.
  * A shared message queue service that allows agents to publish and subscribe to events like object state changes.

In previous chapters you have seen how to create question and answer or command and control expertise.  These types of expertise require the user to initiate the dialog with the Personal Digital Assistant service. This section describes how you can make your expertise initiate the user proactively using the APIs available in the Knowledge and Reasoning service that is included with the Personal Digital Assistant Builder.      

##  Design
It is easier to understand the design approach needed to make an expertise be proactive by using an example.  The example used here shows how a Timer Reminder expertise can proactively engage a user at a certain time   Here are parts of code that must be written to achieve this use case.

* **Client application**: Determines how the user will interact with the expertise
  * Browser using a NodeJS Web application to interact with our expertise.
* **Expertise**:  Determines the task or better decision that the will be accomplished.
  * Reminds the user at a specific time
* **Object**:  The objects that must be reasoned about and used expertise agents to be triggered.  The Reminder object has these **states**:
  * Set
  * Notify
  * Acknowledge
  * Disabled   
* **Rules**:  
  * Reminder agent that will poll the Time object for events for when it needs to invoke the reminder to the user.
  * Time agent that will poll the Time object for events for when it needs to notify the user.
* **Rules**:  Conditions that determine when a event should trigger an action.
  * If the object reminder state is notify then the reminder expertise will notify the user of their reminder.
  * Rules client side code.


## Scenario steps diagram

| Reminder expertise and agent                      | Reminder topic                       |      Other agents                                                                           |
|:--------------------------------------------------|:-------------------------------------------|:--------------------------------------------------------------------------------------|
| 1. User sets alarm using the reminder expertise   | state="set" time=1:30 PM EST         | 2.  Alarm agent checks time and looks at topic for Reminder state="set" and time=now        |
|                                                   | state="set" time=1:30 PM EST         | 3.  1:30 PM Alarm agent checks time and looks at topic for Reminder state="set" and time=now|
|                                                   | state="notify" time=1:30 PM EST      | 4.  1:30 PM Alarm agent sets Reminder topic state="notify"                                  |
| 5. Reminder agent checks topic for state="notify" | state="notify" time=1:30 PM EST      |                                                                                             |
| 6. Reminder expertise notifies the user           | state="notify" time=1:30 PM EST      |                                                                                             |
| 7. User acknowledges the alarm                    | state="acknowledge" time=1:30 PM EST |                                                                                             |
| 8. User turns off the alarm                       | state="disabled" time=1:30 PM EST    |                                                                                             |


### What's happening in step 1
* At 1:30 pm the user asks the Reminder expertise to notify him/her in 30 Mins.
* Reminder expertise sets the Reminder object topic "state" to "set" and "time" to 1:30 PM
* Reminder object agent subscribes to the Reminder object state message topic for "state" to "notify"

### What's happening in step 2, 3 and 4
* Alarm object agent continuously checks the current time and monitors the Reminder topic that matches state="set" and time=now
* When the Alarm object finds a reminder that matches, it updates the Reminder topic state to "notify"

### What's happening in steps 5, 6 and 7
* Reminder agent checks detects the state="notify"
* Reminder expertise notifies the user
* User acknowledges the alarm by snoozing or disabling the reminder

## Implementation
How to implement?
### Create the objects in

## Create the topic

## Create the agents

## Use agents to publish and read from the topic

## Integrate with the expertise

> **What next?** Learn how about [Objects]({{site.baseurl}}/knowledge/objects/)
