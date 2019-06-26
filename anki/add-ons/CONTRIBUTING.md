

<h2 align="center">How to Contribute to my Anki Add-ons</h2>
<p align="center"><img src="https://glutanimate.com/logos/banner.svg"></p>

:wave: Hi! Thanks for deciding to contribute! The following document tries to summarize all of the different ways in which you can support the development of my add-ons, be it as an end-user or programmer.


**Table of Contents**
- [Supporting my Work Directly](#Supporting-my-Work-Directly)
- [Reporting a Bug or Suggesting a New Feature](#Reporting-a-Bug-or-Suggesting-a-New-Feature)
- [Contributing to the Codebase](#Contributing-to-the-Codebase)
  - [Scope of Changes](#Scope-of-Changes)
  - [Coding Style Conventions](#Coding-Style-Conventions)
  - [Submitting a Pull Request](#Submitting-a-Pull-Request)


### Supporting my Work Directly

Are you eager to contribute, but don't have the ability/time to work on the project yourself? Then please consider using one of the buttons below to support my efforts by pledging your support on <strong>Patreon</strong>, or by buying me a <strong>coffee</strong>. Each and every contribution is greatly appreciated and will help me maintain and improve my Anki add-ons as time goes by!

<p align="center">
<a href="https://www.patreon.com/glutanimate" rel="nofollow" title="Support me on Patreon 😄"><img src="https://glutanimate.com/logos/patreon_button.svg"></a>      <a href="https://ko-fi.com/X8X0L4YV" rel="nofollow" title="Buy me a coffee 😊"><img src="https://glutanimate.com/logos/kofi_button.svg"></a>
</p>

<p align="center">
<i>Thank you!</i>
</p>



### Reporting a Bug or Suggesting a New Feature

This section guides you through submitting bug reports and feature requests. Following these guidelines helps the community and me to understand your report, reproduce the behavior, and find related reports.

> **Note**: Most of the actions below require that you [sign up to GitHub](https://github.com/join). Registration only takes a moment and allows you to participate in the development of all of your favorite Anki add-ons (not just mine!).
> 
> Using the issue tracker on GitHub is the fastest way to get in touch with me, as I don't get notified of your reviews or forum posts. It also greatly reduces my workload because formalities such as checking for existing reports and asking for debug information are automatically taken care of.
> 
> You can also contact me by submitting a new thread on Anki's [αdd-on support forums](https://anki.tenderapp.com/discussions/add-ons), or messaging me at <a href="mailto:ankiglutanimate@gmail.com?subject=Support%20request%20concerning%20&lt;add-on&gt;%3A&amp;body=Please%20describe%20your%20request%20here%20while%20providing%20as%20many%20details%20as%20possible%20(e.g.%20exact%20instructions%20to%20reproduce%20the%20problem,%20screenshots, info%20about%20your%20Anki%20version%20and%20operating%20system,%20etc.) "><img src="https://glutanimate.com/logos/email.svg"> ankiglutanimate@gmail.com</a>, but the issue tracker is the fastest way to get my attention.

Here is how you would ideally report a bug or suggest new feature:

1. Start by clicking on the issues tab of the repository in question.:

    <img src="https://help.github.com/assets/images/help/repository/repo-tabs-issues.png">

    If you don't know how to find the repository of a particular add-on: It's usually linked at the bottom of the description text on AnkiWeb (just search for 'github' on the page).

2. Next, please ensure that the bug or suggestion has not been submitted before by performing a cursory search through the existing issues:

    <img src="https://help.github.com/assets/images/help/issues/issues_search_bar.png">

3. If you're unable to find an open issue, click on **New Issue** to open a new one:

    <img src="https://help.github.com/assets/images/help/issues/new_issues_button.png">

4. If there are multiple issue types, click **Get started** next to the type of issue you'd like to open:

    <img src="https://help.github.com/assets/images/help/issues/issue_template_get_started_button.png">

5. Make sure to fill out the provided **description template** as best as you can, and enter a descriptive **title** that concisely summarizes the issue.

6. When you're finished, click **Submit new issue**.




### Contributing to the Codebase

#### Scope of Changes

Reviewing and testing outside changes takes time. A patch or pull request should therefore be the minimum necessary to address one issue. Please don't make a pull request for a bunch of unrelated changes, as they are likely to be rejected – split them up into separate requests instead.

Small patches that fix a specific problem and don't affect other functionality are more likely to be merged than broader changes that affect many parts of the code. If in doubt, please ask before you begin work on them so your work does not go to waste. The easiest way to get in touch with me is [opening an issue](https://help.github.com/en/articles/creating-an-issue) in the corresponding repository and, when prompted, selecting the _Question_ option.

It is important that your changes maintain the same level of compatibility as the existing code. For add-ons that support both Anki 2.0 and 2.1, you will have to refrain from using any features or idioms only supported by Python 3, Qt 5, or Anki 2.1.

You can find out which level of compatibility the add-on currently supports by looking at the `targets` key in the `addon.json` file at the very top of the repository. Should the repository not include an `addon.json` file, then please try to follow whatever compatibility specifications are noted on the AnkiWeb page of the add-on (usually linked at the top of the repository).

#### Coding Style Conventions

_Overview_

For consistency, changes should maintain the existing code style that is inspired by [Anki's code base](https://github.com/dae/anki/blob/master/README.contributing):

- < 80 column lines
- succint variable names
- naming conventions: `camelCase` for function and method names. `PascalCase` for class names. `snake_case` for other variables.
- outside of that: general adherence to [PEP8](https://www.python.org/dev/peps/pep-0008/)

_Linting_

Before submitting your changes, I recommend running them through a linter like [flake8](http://flake8.pycqa.org/en/latest/). The following command should more or less reflect the coding conventions listed above:

```bash
flake8 --ignore=F405,F408,F403,E302,E303,E305,W293,N802,E266,N806,E226,E402 --exclude=forms,resources src
```

If you prefer [pylint](https://www.pylint.org/), feel free to run it against the [configuration Anki uses](https://github.com/dae/anki/blob/master/.pylintrc).

#### Submitting a Pull Request


1. [Fork the repository and clone it to your local disk](https://help.github.com/en/articles/fork-a-repo)

2. On your local copy of the repository, switch to the main development branch (if not otherwise noted this is the `master` branch):

        $ cd <repo_name>
        $ git checkout master

3. Create a branch to hold your changes and start making changes. **Do not work on the master branch!**

         $ git checkout -b my-feature

4. When tracking your changes through commits, please follow these guidelines:
    - Concisely summarize your changes with informative commit messages. For a general guide on writing commit messages please see [here](https://github.com/erlang/otp/wiki/writing-good-commit-messages).
    - Try to limit your commits to a minimum amount to avoid crowding up the revision history.
    - If you can sensibly group the changes under one commit (i.e. squash them), please do so.

5. Push your changes to GitHub with

        $ git push -u origin my-feature

6. [Create a pull request](https://help.github.com/en/articles/creating-a-pull-request) with your changes

7. If you are presented with a description **template**, try to fill it out as best as you can. Otherwise try to succinctly summarize the problem you're addressing and the scope of your changes. Should your PR address an existing issue report, please link to it.
8.  Add a descriptive title that summarizes your changes at a glance.
9.  Submit your pull request for review.

For more information on working with Git and GitHub please see [GitHub's help center](https://help.github.com/en).



---

Parts of this document were inspired by Anki's [contribution guidelines](https://github.com/dae/anki/blob/master/README.contributing).