# Developer Learning Experience
This repository is for creating the key documentation assets for the Consumer IoT developer learning experience.  
This includes:
* [Documentation](https://watson-personal-assistant.github.io/developer)
* Tutorials for getting started
* Samples
* Code snippets
* API reference

# Contributing
## Documentation
Simply go to the [documentation page](https://watson-personal-assistant.github.io/developer) documentation page and click on the edit icon at the top of the page.  If you aren't a member of the repo do a pull request for the page you want to fix or add.

If you want to add a section, edit the `_data/sections.yml` page and then create new directory with same name in the `_content` directory then create files under that with the first 4 lines being...
```
---
title: Title of page
weight: 10
---

``` 

The weight value controls the order of the files in the side bar.
