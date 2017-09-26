---
title: Accessing the WPA Builder service
weight: 10
---
## Register for the WPA Builder service
The Watson Personal Assistant (WPA) Builder service is an internal IBM private beta that is hosted on Bluemix and is available right now.   Access requests are reviewed and approved by the WPA Builder service administrator.   

Complete this beta request [access form]() to join the private beta.  If approved, you will be sent the necessary information to access the WPA Builder service. 

### API key
An API key allows you to programmatically access the WPA Builder service.  An API key uniquely identifies the developer organization that is creating expertise or applications that use the WPA Builder service.  The key is also used for monitoring purposes. API keys should be stored in environment variables or env files and used when making API requests to the Personal Assistant Builder service.  See example expertise implementations for how to use an API key.

### Service URL and API key
Once you have been approved for the WPA Builder beta, you will be provided with an API Developer URL that looks something like this:
https://watson-personal-assistant-toolkit.mybluemix.net/?api_key=673b5a19-37d6-bccf-e0b2-169f7a105e07

Your API key consists of the digits that follow "api_key=" in the URL.  Use this URL when making API calls to the service.

### Other service API keys
If your WPA Builder application or expertise includes other Bluemix or Watson Services, you must also provision and manage those keys separately.   

## Creating tokens
Tokens are used to authorize a device to access the WPA Builder Voice service that includes a websocket server.  A user can speak utterances into a device and send them to the WPA Builder Voice service.  The WPA Builder Voice service converts the utterances into text using the Speech to Text service and then onto the WPA Builder service.

Tokens can be created by the WPA Builder application developer.  They are bound to the authenticated user using the device. 

- To create a token, see the [instructions]() in the Authentication section.
- Tokens are only valid for 1 hour. 

>**What next?**  Learn about the basics ["to get started"]({{site.baseurl}}/developer/get-started/get-started/)
