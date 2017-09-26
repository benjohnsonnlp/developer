---
title: What are personal assistant applications?
weight: 10
---
## Personal assistant applications

A personal assistant application helps user's with their needs within the context of an space or journey by effortlessly connecting the user with the choices they have made for being provided assistance.

The personal assistant application can anticipate a user's needs and proactively suggests help before, during and after their experience. This is done using the Knowledge and Reasoning API's.

The scope of assistance is determined based on the expertise the user or an administrator has chosen to enable and that is available in their application.  Expertise can be invoked generically or specialized to use “Order a pizza” vs “Order Domino’s Pizza”. Personal Assistant applications remembers your past experiences.

Check to see if someone has already created an personal assistant that you can use in the Watson Personal Assistant Builder expertise git repository.

## Space

A space helps identify what are the available compatible, trusted, customizable and personal choices for personal assistant users.   It allows both designers and developers to better understand and explain the scope of scope the user experience to design for.  It helps end users better understand how their choices will be limited to.  Choices include:

* Expertise
* Devices
* Share my experience with other users
* Remember my experience or don’t
* Location

## Cognitive profile

Work is underway to support cognitive profiles.  A cognitive profile are a user's customized set of choices for a Personal Assistant application and or those that are personalized for them.  These can include:

* To share or not share my experience with others
* Suggest, remember or forget my experience
* Allowed devices and expertise
* Location - which one FL, CA, EU
* Has context - Where “home” is when studying abroad temporarily
* Other personal preferences

## Context

Personal Assistant applications have context.  Provides background information that further clarifies the meaning of a location, interaction or user.  The conditions around a situation, setting, location time, user and devices that are involved.  Here are some examples. Context helps reduce the number of questions a user has to answer during a session.  Context is passed in each request to the Personal Assistant Builder service.

**Home**
* A user's current location or other location like a student (user) wants to go ''home''.  
* The context for ''home'' during the school year (time) is the dorm room on campus at the university he is attending
* The context for ''home'' during the summer and school breaks are his parents primary address and not vacation address

> **What next?** [Learn how to build a personal assistant application]({{ site.baseurl }}/cognitive-application/build-applications/)

Help [contribute]({{ site.baseurl }}/contribute/contribute-doc/)
