---
title: Help us improve
weight: 10
---

There are a variety of ways you can help improve Watson Assistant Builder service. Contribute back to the developer community in the following ways:

* Provide us [feedback on this form]({{site.baseurl}}/broken_link)
* Answer questions on Stack Overflow - *Need tags we will use.*
* Answer questions on IBM Developerworks - *Need forum we will use.*
* Improve the Watson Assistant Builder [documentation](https://github.com/Watson-Personal-Assistant/developer)
* Create and share your own [expertise]({{site.baseurl}}/expertise/build-expertise/) and client application integrations.
* Blog about your experiences.
* Share your success stories and use cases in this section.

## How to improve this documentation

### Add/Modify content
Edit content in pages immediately right in the browser or edit `.md` pages under the `_content` directory.

### Add new pages
You can add new pages for missing content by copying an existing page in the section as template.  Pages are formatted using [kramdown](https://kramdown.gettalong.org/quickref.html).  See [Quick Reference]({{site.baseurl}}/broken_link) on how to add new pages. Remember to add the pages to the right folders that map to the sections.

### Add new sections
Add new sections to this documentation in the browser [Quick Reference on how to add sections]({{site.baseurl}}/broken_link).

### Edit the home page
To change the home page, edit `index.md`.

### How to edit and view locally
You can edit and view documentation pages on your local environment. It is helpful to see what your content looks like formatted in the page before you push changes to github.  These pages are under git version control.

Clone repository

`git clone https://github.com/watson-personal-assistant/developer.git`

### Install Jekyll
Watson Assistant Builder documentation uses Jekyll to build HTML files from the markdown source. To install Jekyll do the following command.  (Note, on MacOS Jekyll requires Xcode command line tools `xcode-select --install` should install the latest.  See [Jekyll install](https://jekyllrb.com/docs/installation/) for complete documentation if the steps below don't work.)

`sudo gem install jekyll bundler`

Check that Jekyll is working

`jekyll --version`

If you get errors like "Could not find public_suffix" change directory out of the `developer` directory created by the "git clone" command and try again.

This documentation has been known to work with version `jekyll 3.4.3`

Install the bundles required

`cd developer`

`bundle install`


### Start Jekyll
To start Jekyll and see edit changes running locally:

`cd developer` (if not already in the developer directory)

`.bin/develop`

You might see some "npm ERR!" messages but they are harmless.  As long as you see something like "Server address: http://127.0.0.1:4000/" and "Server running... press ctrl-c to stop". Then the jekyll process is running correctly.

Go to that address to see the documentation site running locally . Do a browser refresh to see any edits.
