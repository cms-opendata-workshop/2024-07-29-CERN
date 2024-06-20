[![Website](https://github.com/carpentries/workshop-template/actions/workflows/website.yml/badge.svg)](https://github.com/carpentries/workshop-template/actions/workflows/website.yml)

# CMS Open Data Workshop 2024

This is the main repository for the [CMS Open Data Workshop 2024](https://cms-opendata-workshop.github.io/2024-07-29-CERN/) event.  The workshop is based on  The Carpentries' ([Software Carpentry][swc-site], [Data Carpentry][dc-site], and
[Library Carpentry][lc-site]'s) templates for creating websites for workshops.  In particular, we followed the instructions in the official [workshop template repository](https://github.com/carpentries/workshop-template) and used the "template" function to make a copy and customize it.  As it is explained there, it builds automatically on Github.

## How to contribute

In order to modify the main workshop website, i.e., this repository, please follow the SW Carpentry's [default instructions](https://github.com/carpentries/workshop-template#customizing-your-website-required-steps).

## How to add lessons to this workshop

**The cms-opendata-workshop organization has its own Carpentries workbench template.** 
To use this template to start a new lesson repository, 
make sure you're logged into Github.   
Visit https://github.com/cms-opendata-workshop/workbench-template-md/generate
and follow the instructions.
Checking the 'Include all branches' option will save some time waiting for the first website build
when your new repository is initialised.

If you have any questions for DPOA, ask on Mattermost!. If you have any questions for the carpentries developer, contact [@tobyhodges](https://github.com/tobyhodges)

## Configure a new lesson

Follow the steps below to
complete the initial configuration of a new lesson repository built from this template:

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
   Check the "Use your GitHub Pages website" option,
   and [add some keywords and other annotations to describe your lesson](https://cdh.carpentries.org/the-carpentries-incubator.html#topic-tags)
   in the _Topics_ field.
   At minimum, these should include:
   - `lesson`
   - the life cycle of the lesson (e.g. `pre-alpha`)
   - the human language the lesson is written in (e.g. `deutsch`)

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





Lessons are generally added to the main workshop site from a repository in the current Github organization called [styles](https://github.com/cms-opendata-workshop/styles), i.e., from the [cms-opendata-workshop](https://github.com/cms-opendata-workshop) organization.  If you need to create or modify a lesson, please follow the [instructions below](#creating-a-lesson).  It is important to use the local `styles` repository as it is tailored to CMS needs.

In order to create a new lesson for this workshop, follow the procedure below (which is based on [these](https://carpentries.github.io/lesson-example/setup.html#creating-a-new-lesson) original instructions, but with details concerning this workshop): 

We will assume that the name of your the new lesson is `worshop2024-lesson-temp` (make sure you name it properly, replacing `lesson-temp` with the appropriate name for your lesson.)  

1.  We'll use the [GitHub's importer](https://github.com/new/import) to make a copy of the lesson template in the workshops github organization. (Note: This is like a GitHub Fork, but not connected to the upstream changes)

2.  Put the URL of **[the styles repository](https://github.com/cms-opendata-workshop/styles)**, that is
    **https://github.com/cms-opendata-workshop/styles**, in the "Your old repository’s clone URL" box.  Make sure you do not use the carpentries style repository as this one will not be tailored with CMS logos, etc.

3. Select the owner for the new repository as `cms-opendata-workshop`.

4. Choose a name for your lesson repository. In our example, this is `worshop2024-lesson-temp`. Please follow this pattern, i.e., `workshop2024-lesson-{description}`

5. Make sure the repository is public.

6. You can now click "Begin Import". When the process is done, you can click "Continue to repository" to visit your newly-created repository.

7. In order to properly initialize the lesson repository, you need to work from your local machine or have someone do it for you (after the initialization process is done, you can work directly using the Github browser page).  Clone your newly-created repository to your computer:
    ~~~
    $ git clone -b gh-pages https://github.com/cms-opendata-workshop/workshop2024-lesson-temp.git  # note: replace the name of your lesson
    ~~~

8. Go into that directory using:
    ~~~
    $ cd workshop2024-lesson-temp
    ~~~

9. To be able to pull upstream style changes, you should manually add the
     styles repository as a remote called `template`:
    ~~~
    $ git remote add template https://github.com/cms-opendata-workshop/styles.git
    ~~~
    This will allow you to pull in changes made to the template, such as improvements to our CSS style files.

10. Configure the `template` remote to not download tags:
    ~~~
    $ git config --local remote.template.tagOpt --no-tags
    ~~~

11. Make sure you are using the `gh-pages` branch of the lesson template:
    ~~~
    $ git checkout gh-pages
    ~~~

12. Run `bin/lesson_initialize.py` to create all of the boilerplate files
    that cannot be put into the styles repository
    (because they would trigger repeated merge conflicts).

13. Create and edit files as explained further in
    [the episodes of this lesson](https://carpentries.github.io/lesson-example/index.html#schedule).

14. (requires [Jekyll Setup](#installing-software) from below) If working locally, preview the HTML pages for your lesson:
    ~~~
    $ make serve
    ~~~
    Alternatively, you can try using Docker:
    ~~~
    $ make docker-serve
    ~~~

15. Commit your changes and push to the `gh-pages` branch of your repository:
    ~~~
    $ cd workshopwhepp-lesson-temp
    $ git add changed-file.md
    $ git commit -m "Explanatory message"
    $ git push origin gh-pages
    ~~~
    After a few minutes, your changes should be visible on the live site of the lesson (see #17 below).

16. Do not forget to choose the `gh-pages` branch as the default one: go to the `Settings` option of the new lesson repository, chosee `Branches` from the left menu, and choose the `gh-pages` branch as the default.

17. Finally, in order to facilitate the access to the live site, go to the `Settings` page of the lesson repository, then to the `Pages` option on the left menu, and copy the *live* web link to the `About` description of the main page of you lesson repository.

## Installing Software

If you want to set up Jekyll so that you can preview changes on your own machine before pushing them
to GitHub, you must install the software described in the lesson example [setup
instructions](https://carpentries.github.io/lesson-example/setup.html#jekyll-setup-for-lesson-development).

**Note:**
There might be some issues with the ruby versions.  The default Carpentry instructions may be outdated.  One might need to fiddle a little bit with the installation.  Fortunately, there are external (Google) instructions that can be used to fix potential problems.

## Getting and Giving Help

[email]: mailto:cms-dpoa-coordinators@cern.ch
[customization]: https://carpentries.github.io/workshop-template/customization/index.html
[dc-site]: https://datacarpentry.org
[design]: https://carpentries.github.io/workshop-template/design/index.html
[faq]: https://carpentries.github.io/workshop-template/faq/index.html
[github-project-pages]: https://help.github.com/en/github/working-with-github-pages/creating-a-github-pages-site
[issues]: https://github.com/carpentries/workshop-template/issues
[lesson-example]: https://carpentries.github.io/lesson-example/
[self-organized-workshop-form]: https://amy.carpentries.org/forms/self-organised/
[swc-site]: https://software-carpentry.org
[lc-site]: https://librarycarpentry.org
