---
title: Register expertise and test locally
weight: 30
---
This page will walk you through phase 2 of building your first expertise.

1. [How to run and use the "HelloWorld" boilerplate expertise hosted locally.]({{site.baseurl}}/expertise/build-expertise)
2. **How to register your expertise with the Personal Assistant Builder service and use the local running "HelloWorld" expertise**
3. How to host your "HelloWorld" expertise on Bluemix for others to use.

### Pre-requisite
In the steps below you are required to have a Personal Assistant API Key. See [Get Access]({{site.baseurl}}/get-started/get-api-key/) for how to get your key.  Then in the steps below replace **paste-your-api-key-here** with your API key you receive.

### Step 1: Create an expertise collection in the Personal Assistant
Use the Personal Assistant Builder service **/expertiseCollection** API to create a expertise collection that your expertise will be added to using your API Key and Personal Assistant Builder service Bluemix hosted URL.

`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{
  "name": "example"
}' 'https://watson-personal-assistant-toolkit.mybluemix.net/v1/api/expertiseCollection?api_key=paste-your-api-key-here'`

### Step 2: Setup NGROK
The NGROK application securely tunnels to localhost which is needed to connect the Personal Assistant Builder service running on Bluemix to the expertise running locally on your system. Download and install [NGROK Client](https://ngrok.com) to allow connection to your locally running HelloWorld expertise.  Once you've done that, enter the following command to start a tunnel to your expertise.

`/Applications/ngrok http 10010`

Note the "https://XXXXXXXX.ngrok.io" path that will be displayed; it will be used in the next step.

### Step 3: Add the expertise to the Personal Assistant
Use the Personal Assistant Builder service **/expertise** API to add your locally running expertise to the  using your API Key and Personal Assistant Builder service Bluemix hosted URL.

`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{
  "name": "hello-world",
  "url": "https://XXXXXXXX.ngrok.io"
}' 'https://watson-personal-assistant-toolkit.mybluemix.net/v1/api/expertise?api_key=paste-your-api-key-here'`

### Step 4: Add the expertise to the expertise collection
Use the Personal Assistant Builder service **/expertiseCollection/AttachExpertise** API to link the registered expertise with the collection created earlier using your API Key and Personal Assistant Builder service Bluemix hosted URL.

`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{
  "fallback": false,
  "expertiseNames" : [
    "hello-world"
  ]
}' 'https://watson-personal-assistant-toolkit.mybluemix.net/v1/api/expertiseCollection/AttachExpertise/example?api_key=paste-your-api-key-here'`

### Step 5: Say hello to the Personal Assistant
Use the Personal Assistant Builder service **/converse/expertiseCollection** API to say hello world using your API Key and Personal Assistant Builder service Bluemix hosted URL.

`curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{
  "id": "id-dc6",
  "version": "1.0",
  "language": "en-US",
  "text": "hello",
  "context": {
    "user": {
      "id": "user-f4c"
    },
    "application": {
      "id": "application-14c",
      "attributes": {}
    }
  }
}' 'https://watson-personal-assistant-toolkit.mybluemix.net/v1/api/converse/expertiseCollection/example?api_key=paste-your-api-key-here'`

The JSON returned should include the following:

```
"speech": {
  "text": "Hello world"
},
```

> **What next?** Learn how to [deploy your expertise to Bluemix]({{site.baseurl}}/expertise/deploy-to-bluemix/)
