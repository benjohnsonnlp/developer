---
title: Setup local development environment
weight: 50
---
This section explains how to setup your local development environment so that you can test your expertise locally and then deploy them to Bluemix Cloud Foundry runtime Using Bluemix you can use many of the Bluemix services to power you expertise.

## Setup Bluemix  
1.  If you don't have a Bluemix Account [Sign up for Bluemix.net](https://console.ng.bluemix.net/registration/)
2.  Download Bluemix [CLI](https://console.ng.bluemix.net/docs/cli/index.html#cli)
3.  Download or use your preferred IDE ( Atom, Sublime, Eclipse )
4.  Use [Bluemix CLI](https://console.ng.bluemix.net/docs/cli/index.html#downloads) to create Watson Conversation Service that will be used by the expertise.
5.  Download and use NGROK. https://ngrok.com/download to run expertise locally $ ./ngrok help $ ./ngrok http 5000  to allow the Personal Assistant Builder service to call your local running expertise.

## Setup NodeJS
1.  Install [NodeJS](https://nodejs.org/en/)
2.  Install [NPM](https://docs.npmjs.com/cli/install) for NodeJS dependency management
3.  Install [Git](https://git-scm.com/downloads)

## Setup Python
1.  Install [Python](https://nodejs.org/en/)
2.  Install [PIP](https://pip.pypa.io/en/stable/reference/pip_download/#pip-download) for Python dependency management
3.  Install [Git](https://git-scm.com/downloads)

> **What next?** Learn how to build your first [expertise]({{ site.baseurl }}/expertise/build-expertise/)

--------
Help [contribute]({{site.baseurl}}/contribute/contribute-doc/)
