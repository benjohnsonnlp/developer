---
title: The Knowledge and Reasoning tutorial
weight: 10
---

In the following, we will walk through the creation of a simple home security scenario using the Knowledge and Reasoning component.

In this scenario, the user would like to be notified if their house's entrance door is opened while he/she is away.

This scenario is implemented using the following:
1. **Door Sensor Input Agent**: An agent that interprets the raw sensor data received by the door and updates the door status accordingly.
2. **Door Alert Generation Rule**: A rule that, for each door status change, checks if the door has been opened while the relevant house owners are away.
If so, this rule inserts a "SecurityAlert" object  into the common data store.
3. **Notification Rule**: A rule that notifies a user when a relevant alert has been added to the data store.

NOTE:  only (2) and (3) are represented as Agent objects in the example code, because (1) does not need to be an agent:  it does not listen for world model changes.

The end to end flow is enabled by the rules communicating with each other through the shared data store and publish/subscribe mechanism. In the data store, two types of data can be stored: **Objects**, such as door, house, notification, person, and the **Relations** 
between these objects. Therefore the data model of the scenario must be defined in terms of these objects and relations.

> **What next?** Learn how to [create objects in Knowledge component]({{site.baseurl}}/knowledge/create-objects).
