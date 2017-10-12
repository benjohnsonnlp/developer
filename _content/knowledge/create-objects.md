---
title: Create object and relations
weight: 20
---
This page will walk you through first phase of making your assistant proactive.  In this phase of the tutorial, you will create objects and relations programmatically using the Watson Assistant Knowledge and Reasoning components NodeJS SDK.

1. **How to create objects and relations in the Knowledge component**
2. How to create rules in the Reasoning component
3. How to create an agent and run it locally
4. Publish the agent to Bluemix

### Pre-requisite
Make sure you have already [setup your local development environment]({{site.baseurl}}/expertise/setup-local-dev-env/)

### Step 1: Fork the Knowledge and Reasoning SDK
1. Go to  [https://github.com/Watson-Personal-Assistant/kr-node-sdk]({{site.baseurl}}/broken_link).
2. Click the gray **Fork** button in the top right corner.


### Step 2: Clone your fork of the SDK
1. Click the green **Clone or download** button.
2. Copy the `https` path.
3. Using the Terminal app, do command

    `git clone your-github-url`
    
### Step 3: Create a javascript file and add includes

Create a new file named `myapp.js` and include the object, relation objects and dotenv module.

```javascript
require('dotenv').config();
var KnowledgeObject = require('./sdk/object');
var KnowledgeRelation = require('./sdk/relation');
```

### Step 4: Create objects for the tutorial

Using the `KnowledgeObject` object define a function to create a `Person`, `House`, and `Door` with the following code:

```javascript
var createObjects = function() {

  person = new KnowledgeObject('Person',
      {
        'name': 'TestBen',
        "latitude": 12.456,
        "longitude": 67.99
      }
  );

  house = new KnowledgeObject('House',
      {
        "latitude": 12.345,
        "longitude": 67.890,
        "name": "home"
      }
  );

  door = new KnowledgeObject('Door',
      {
        "isOpen": false,
        "name": "Front door"
      }
  );
};
```

### Step 5: Create relationships between the objects

Using the `KnowledgeRelation` object define a function to create two relationships; one called `ownership` for `person` to `house` and another named `has-as-part` for `house` to `door`.

```javascript
var createRelations = function() {
  personToHouse = new KnowledgeRelation(
    'ownership', person, house);

  houseToDoor = new KnowledgeRelation(
    'has-as-part', house, door);
};
```

### Step 6: Call creation functions to create the objects and relations in the Knowledge component

Create a promise that creates the KnowledgeObjects and then creates the KnowledgeRelations if successful using the following code:

```javascript
Promise.all(
    [
      createObjects(),
      person.create(),
      house.create(),
      door.create()
    ]
).then(
  function (results) {
    console.log('All objects created\n\n');

    Promise.all(
        [
          createRelations(),
          personToHouse.create(),
          houseToDoor.create()
        ]).then(
          
        function (results) {
          console.log('All relations created\n\n');
        }
    );
  }
);

```

### Step 7: Create .env file, add Watson Assistant API key and execute

Before the code above can be ran, we need to create a .env file that includes the URL to Watson Assistant and the API key.  

To do this copy the `.env.sample` file to `.env` and edit the `.env` file to have the following:

```
HUB_URL=https://watson-personal-assistant-toolkit.mybluemix.net/
API_KEY=your-API-key
AGENT_PORT=
AGENT_HOST=[this will need to be publicly visible; perhaps you should try ngrok]
```

After providing the Watson Assistant `URL` and `API key`, install the necessary node packages to run the code by using command:

`npm install`

Then run the code by using the command:

`node myapp.js`

If all runs correctly, you should see output similar to:

```
Saved object with id:  4152 and type: House
Saved object with id:  4272 and type: Person
Saved object with id:  4144 and type: Door
All objects created


Created relation: 4272 (Person) -[ownership]-> 4152 (House)
Created relation: 4152 (House) -[has-as-part]-> 4144 (Door)
All relations created
```

If the code fails to run, you might try attaching the chrome devtools using command:

`node --inspect --debug-brk myapp.js`.


Hopefully, all goes well and you have create 3 objects and 2 relations in your Watson Assistant Knowledge component.

> **What next?** Learn how to [create rules in Reasoning component]({{site.baseurl}}/knowledge/create-rules).
