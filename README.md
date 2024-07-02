[![Website](https://github.com/carpentries/workshop-template/actions/workflows/website.yml/badge.svg)](https://github.com/carpentries/workshop-template/actions/workflows/website.yml)

# CMS Open Data Workshop 2024

This is the main repository for the [CMS Open Data Workshop 2024](https://cms-opendata-workshop.github.io/2024-07-29-CERN/) event.  The workshop is based on  The Carpentries' ([Software Carpentry][swc-site], [Data Carpentry][dc-site], and
[Library Carpentry][lc-site]'s) templates for creating websites for workshops.  In particular, we followed the instructions in the official [workshop template repository](https://github.com/carpentries/workshop-template) and used the "template" function to make a copy and customize it.  As it is explained there, it builds automatically on Github.

## How to contribute

In order to modify the main workshop website, i.e., this repository, please follow the SW Carpentry's [default instructions](https://github.com/carpentries/workshop-template#customizing-your-website-required-steps).

## How to add lessons to this workshop

**The cms-opendata-workshop organization has its own Carpentries workbench template.** 
To use this template to start a new lesson repository, make sure you're logged into Github.   
Visit https://github.com/cms-opendata-workshop/workbench-template-md/generate and give the following settings:

* Check "include all branches"
* Choose **cms-opendata-workshop** as the owner of the new lesson
* Choose a lesson name like **workshop2024-lesson-XXXX**, replacing "XXXX" with an informative name
* Provide a description
* Make the lesson repository public

If you have any questions for DPOA, ask on Mattermost!. If you have any questions for the carpentries developer, contact [@tobyhodges](https://github.com/tobyhodges)

## Configure the new lesson

Follow the steps below to complete the initial configuration of a new lesson repository built from this template:

1. **Make sure GitHub Pages is activated:**
   navigate to _Settings_,
   select _Pages_ from the left sidebar,
   and make sure that `gh-pages` is selected as the branch to build from.
   If no `gh-pages` branch is available, check _Actions_ to see if the first
   website build workflows are still running.
   The branch should become available when those have completed.
1. **Adjust the `config.yaml` file:**
   this file contains global parameters for your lesson site.
   Individual fields within the file are documented with comments (beginning with `#`)
   At minimum, you should adjust all the fields marked 'FIXME':
   - `title`
   - `created`
   - `keywords`
   - `life_cycle` (the default, _pre-alpha_, is the appropriate for brand new lessons)
1. **Annotate the repository** with site URL and topic tags:
   navigate back to the repository landing page and
   click on the gear wheel/cog icon (similar to ⚙️) 
   at the top-right of the _About_ box.
   Check the "Use your GitHub Pages website" option

## Notes for CMS Open Data lessons

In principle, there is no need to install R or Pandoc -- rather than building lessons locally, the github actions can be used to render the site after making a push. Note, however, that the content should be in [Pandoc-flavored Markdown](https://pandoc.org/MANUAL.html). If one wishes to test locally, the instructions are provided in [The Carpentries Workbench][workbench] documentation.

**The setup instructions should be written in `learners/setup.md` and the separate pages under `episodes`.**

The `md-outputs` branch shows after setting up the repository. No need to merge them.

The schedule shows only in the "Instructor view": https://cms-opendata-workshop.github.io/workshopqcd-2024-lesson-docker/instructor/index.html 
Use this link if you want to show it.

### Updating an old lesson to the new template

You might consider the information and tools for lesson transition here: https://carpentries.github.io/workbench/faq.html#lesson-transition
But we have not tried them!

If doing it by hand:

1. Change questions (note the empty line after items), objectives and keypoints to
   ```
   :::::: questions
   - question 1
   - question 2

   ::::::

   :::::: objectives
   - objective 1
   - objective 2

   ::::::

   <!-- EPISODE CONTENT HERE -->

   :::::: keypoints
   - keypoint 1
   - keypoint 2
   ::::::
   ```
2. Remove the double quotes of the question, objectives and keypoints.
3. Make sure that keypoints are at the end of the text.
4. Find all `{: .callout}`, `{: .challenge}`, `{: .testimonial}` etc tags and and remove the preceeding `> ` for the block and change them to

   ```
   ::: callout
   This is a callout block. It contains at least three colons
   :::
   ```
   or

   ```
   ::::::::::::::::::::::::::::::::::::: challenge

   ## Question

   Q: question

   :::::::::::::::: solution

   A: answer

   :::::::::::::::::::::::::
   :::::::::::::::::::::::::::::::::::::::::::::::
   ```

### Documentation

See e.g.

- https://carpentries.github.io/lesson-development-training/
- https://carpentries.github.io/sandpaper-docs/index.html

### Indents and unexpected code blocks

Note that double-indent (two tabs) or anything more that three spaces produces a code block. That's not necessarily what one would expect.
Also, in some special cases, in nested lists, the second level items might appear as a code block.
 
### Figures

Figures should be located under `episodes/fig`, and included, for example, with

```
![](fig/portal_screenshot_landing_page.png)
```

## Getting and Giving Help

[email]: mailto:cms-dpoa-coordinators@cern.ch
