---
title: Accessing the Watson Personal Assistant Builder service
weight: 10
---
## Register for the Watson Personal Assistant Builder service
The Watson Personal Assistant Builder service is an internal IBM private beta that is hosted on Bluemix and is available right now.   Access requests are reviewed and approved by the Watson Personal Assistant Builder service administrator.   

Complete this beta request [access form]() to join the private beta.  If approved, you will be sent the necessary information to access the Watson Personal Assistant Builder service. 

### API key
An API key allows you access to the Watson Personal Assistant Builder service.  An API key uniquely identifies the developer organization that is creating expertise or applications that use the Watson Personal Assistant Builder service.  The key is also used for monitoring purposes. API keys should be stored in environment variables or env files and used when making API requests to the Personal Assistant Builder service.  See example expertise implementations for how to use an API key.

### Accessing the service
Once you have been approved for the Watson Personal Assistant Builder beta, you will be provided with an API key that looks something like this:

`673b5a19-37d6-bccf-e0b2-169f7a105e07`

Head to the [https://watson-personal-assistant-toolkit.mybluemix.net](https://watson-personal-assistant-toolkit.mybluemix.net) website and paste your key into the text field to then access your instance of the Watson Personal Assistant Builder service. From there you can; access this documentation, access Swagger UIs for the various APIs and test your personal assistant with a simple text-based chat.

### Other service API keys
If your Watson Personal Assistant Builder application or expertise includes other Bluemix or Watson Services, you must also provision and manage those keys separately.   

## Creating tokens
Tokens are used to authorize a device to access the Watson Personal Assistant Builder Voice service that includes a websocket server.  A user can speak utterances into a device and send them to the Watson Personal Assistant Builder Voice service.  The Watson Personal Assistant Builder Voice service converts the utterances into text using the Speech to Text service and then onto the Watson Personal Assistant Builder service.

Tokens can be created by the Watson Personal Assistant Builder application developer.  They are bound to the authenticated user using the device. 

- To create a token, see the [instructions]() in the Authentication section.
- Tokens are only valid for 1 hour. 

>**What next?**  Learn about the basics ["to get started"]({{site.baseurl}}/get-started/get-started/)
