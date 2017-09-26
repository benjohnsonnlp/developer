---
title: Build your first expertise
weight: 20
---
This page will walk you through the first phase of building your first expertise. You will create your expertise programmatically using the Watson Personal Assistant Builder REST APIs that are accessible in Swagger API reference.

1. **How to run and use the "HelloWorld" boilerplate expertise hosted locally.**
2. How to register and use the local running "HelloWorld" expertise with Personal Assistant Builder service.
3. How to host your "HelloWorld" expertise on Bluemix for others to use.

### Pre-requisite
Make sure you have already [setup your local development environment]({{site.baseurl}}/developer/expertise/setup-local-dev-env/)

### Step 1: Fork the boilerplate
1. Go to  [https://github.com/Watson-Personal-Assistant/ExpertiseBoilerPlateRemote](https://github.com/Watson-Personal-Assistant/ExpertiseBoilerPlateRemote).
2. Click the gray **Fork** button in the top right corner.

### Step 2: Clone your fork of the boilerplate
1. Click the green **Clone or download** button.
2. Copy the `https` path.
3. Using the Terminal app, do command

    `git clone https://github.com/Watson-Personal-Assistant/ExpertiseBoilerPlateRemote`

### Step 3: Install the node dependencies
1. Change directory into your ExpertiseBoilerPlateRemote project directory

    `cd ExpertiseBoilerPlateRemote`

2. Install dependencies using command

    `npm install`


### Step 4: Run the expertise
1. Start the expertise using command

    `npm run start`

### Step 5: Test the "HelloWorld" expertise by having a conversation
The Personal Assistant Builder service Converse API allows you to have a conversation with your expertise.   You can test the expertise using a browser and the Swagger API reference page.  Send the "Hello" utterances in a request to the expertise.  
1. Click link [https://localhost:10010](https://localhost:10010) to open browser to Swagger API reference.
2. Click on **Converse**.
3. Click on **/converse**.
4. Paste the JSON below into the **input** text area to say "Hello" to Watson.

    `{
      "id": "001",
      "text": "Hello",
      "version": "1.0",
      "attributes": {
        "intent": "hello-world"
      },
      "context": {
        "user": {
          "id": "user-001"
        },
        "application": {
          "id": "app-001",
          "attributes": {
          }
        },
        "session": {
          "new": true,
          "attributes": {
          },
          "version": "1.0"
        }
      }
    }`
    
5. Click the **Try it out!** button.
6. Watson responds by saying "Hello world".  You can see the response in the returned JSON "text" attribute below. This response would be delivered by a client application like a chatbot.

```JSON
{
  "reject": false,
  "error": 200,
  "shouldEndSession": true,
  "captureInput": false,
  "speech": {
    "text": "Hello world"
  },
  "context": {
    "application": {
      "id": "app-001",
      "attributes": {}
    },
    "session": {
      "new": true,
      "attributes": {},
      "version": "1.0"
    }
  }
}
```

### Step 6: Use Swagger page to see which intents exist
In the last step, the JSON used to send "Hello" to the expertise also sent along the "intent".  This is required here because we are sending the utterance directly to an expertise, which isn't done in a Personal Assistant application.  The Personal Assistant Builder service of the IBM Personal Assistant will take the utterance, determine the intent, and then send the intent and utterance on to the expertise.  The Personal Assistant Builder service gets the intents from the expertise using the **/intents** API. To see this for yourself, do the following

1. Click link [https://localhost:10010](https://localhost:10010) to open browser to Swagger API reference.
2. Click on **Resources**.
3. Click on **/intents**.
4. Click the **Try it out!** button.

Response:

```JSON
{
  "hello-world": {
    "visibility": "always",
    "entities": []
  }
}
```

### Finish
Now you have a working expertise and next we have to register this expertise to Personal Assistant Builder Personal Assistant Builder service.  Text utterances requests are then sent to the Personal Assistant Builder service to get a response from the registered hello world expertise.

 > **What next?** Learn how to [register and test a local expertise]({{site.baseurl}}/developer/expertise/develop-locally/) using a Bluemix hosted Personal Assistant Builder service   

____
Help [contribute]({{site.baseurl}}/developer/contribute/contribute-doc/)
