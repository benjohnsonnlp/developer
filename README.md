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

If  you want to add a section or add pages read these [instructions]().

## Development
When merging changes, **DO NOT overwrite the `_content` directory**. This is kind of weird, so just use the following and we'll all be much happier.

``` sh
# Make sure you’ve got the starter set as your upstream.
git remote add upstream 

# Merge the changes into your own branch.
git checkout gh-pages    
git merge --no-commit --no-ff upstream master
git reset -- _content # revert updates from path
git commit
```
