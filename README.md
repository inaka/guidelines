# General Inaka Development Guidelines



## Introduction

This document describes the general guidelines we expect **all** our members (a.k.a. _inakos_) to comply with in all of our projects. For code guidelines and best practices regarding specific languages, please refer to the corresponding `inaka/[language]_guidelines` github repo.


## The Inakos

Inaka is a _community of open-source enthusiasts_. This community is not closed to _developers_, some of our members are _project managers_, _QA specialists_, etc. We manage our community collaboratively and we communicate through our private Slack workspace. The community was originally formed by all ex employees of [Inaka](http://inaka.net) but now it's open to anybody else that wants to be part of it.

### Joining the Community

To join our community you have to be invited by a current member, that will then become your _sponsor_. You can get an invitation by contancting [one of us](https://github.com/orgs/inaka/people) directly or you can [send us an email](mailto:inakos@googlegroups.com) requesting an invitation.
Once your invitation is accepted, you'll be _temporarily_ added to our Slack workspace. Then you'll be received by everyone and we'll have a conversation around 3 introductory items that will allow us to know you better:

* How did you become a _developer/project manager/team leader/whatever-you-are_?
* When and why did you decide to be an Inako?
* Something interesting about your life

After that conversation, we'll have an internal meeting with your sponsor and the inakos will decide if they let you in. If so, you'll then get access to all of our stuff, including this github organization, our private slack rooms and other resources.


## Specific Guidelines for your Language

In this same repo we also have several other guideline files, specifically tailored to some languages or platforms (e.g. [iOS](IOS.md), [Android](ANDROID.md), [Erlang](ERLANG.md), [Elixir](ELIXIR.md), etc.). Check them out to find out how we work in those particular cases.

## How we use Github Issues

For project tracking we use [Github Issues](https://guides.github.com/features/issues/). Below you'll find our particular rules on how to use this system.

### For Issue Reporters

* Issues need to be set up as detailed as possible. Separate UI from functional tasks. Add detailed descriptions and try to separate them so as to have each task as close to being one-day (or less) in duration as possible.
* Design / UI tasks always need to have a screenshot attached in the task.
* Milestones need to be added, as well Release Dates.
* Never mix different issues in one. Close the original issue and open a new one, if needed.
* Always label issues (ios, android, server, admin, design, etc.).
* If there is an issue that says "XXX is not working correctly", it should also include an explanation on how it should work, for example: if the pivotal title is "The text in the title is right-aligned", the description or at least a comment in that issue should say something like "The text in the title should be centered".

### For developers

* Make sure you read the whole issue and review attachments before you start working on them. If the tasks are not 100% clear to you, reach out to the author.
* As soon as you start working on an issue, assign it to yourself.
* If you leave a comment or question in the issue, mention the person you need feedback from.
* If you find a bug, create a new issue for it.

---

## TDD

We encourage the use of TDD as a method of development as much as it makes sense. The reasons behind this approach are:

* As a developer, you must *never* submit code that's not tested (either with
  unit tests or otherwise). Therefore, the time you would spend testing your
  changes manually can also be spent writing an automated test for that same
  thing. That comes with an additional benefit: you can repeat that test
  as many times as you want and also get the other devs to automatically run it
  in every change, without actually having to remind and/or describe them how to test such a thing.
* Writing the tests before the actual code forces you to think about _what_
  your program should do before focusing on _how_ to achieve it. This leads to
  more accurate and, generally, simpler code.
* Having a good test coverage in your code base increases your general trust
  on the written code and allows for easier and safer refactoring, if needed.
* If well written, tests usually work as documentation as well.

### When to incorporate TDD

TDD is not suited for **all** scenarios, but it is recommended when:

* You're working on an API server project.
* You're working on an open-source library.
* Your project involves UI work and your language has the proper tools to
  write tests for it (e.g. rspec).
* You're writing an internal library with no UI pieces.

---

## Version Control

### Github

* All of our projects are hosted on Github under Inaka's organization account.
* When starting a new project, create a new repository for you and add a brief description.
* For a more detailed guide on how to use Git/Github on your day to day tasks, refer to this [Youtube Playlist](https://www.youtube.com/playlist?list=PL75bT2qMwxlWC9PsShtzOy5rBzYjSWPv7) by [@elbrujohalcon](https://github.com/elbrujohalcon).

#### Commit Messages

Good commit messages serve at least three important purposes:

* To speed up the reviewing process.
* To help us write a good release note.
* To help the future maintainers of the code (it could be you!), say five years
  into the future, to find out why a particular change was made to the code or
  why a specific feature was added.

The blog post ["On commit messages"][on-commit-messages] has a nice discussion
about commit messages.

Tip: if it seems difficult to summarize what your commit does, it may be because it includes several logical changes or bug fixes, and are better split up into several commits using `git add -p`.

#### Commit Rules

Check-in/push rules for the main repository/branch are the following:

* Code must compile. All code merged must **fully** compile. This should be
  true for all commits in the history, because if there are commits that don’t
  fully compile, it will be more difficult to use git bisect. Partial commits
  with non-working code can be allowed if, prior to submitting the pull request, the branch is rebased interactively and the partial commits squashed into a single one. If desired, the work progress history can be retained in the extended commit message.

---

## Development Flow

We are an agile development community. This means we tackle projects in an iterative fashion and show results early and often as we progress through a project.

From a project day to day point of view, our developers work with Pull
Requests and Code Reviews. To any one of our developers, the process (in a
nutshell) is as follows:

* Grab a github issue and mark it as started (e.g. let's say you want to work on issue `#123456` which is a story about editing this document).
* Open a branch with your name and the story id on it (e.g. `elbrujohalcon.123456.edit.this.document`).
* Tag all your commits with the story id (e.g. `git commit -m "[#123456] First edition"`).
* Remember you can have one or more commits per story, but no more than one issue # per commit.
* Once done, submit a Pull Request in github and assign one or more colleagues as reviewers.
  * While you wait for the review, you can pick a different task and start this
    process over. If the PR is a blocker, warn whoever is responsible to
    communicate your block.
* When opening a pull request to generate a page on which the changes can be
  discussed, make sure to use a
  [draft pull request](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/about-pull-requests#draft-pull-requests)
  so that it is not merged. When the discussion concludes,
  [mark it as "ready for review"](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/changing-the-stage-of-a-pull-request#marking-a-pull-request-as-ready-for-review)
  and notify the reviewer so they can merge the pull request.
* The reviewer will then write comments on the PR and you'll have the chance to
  discuss them and/or fix them.
* When the review is done, your reviewer will merge your code into master.
* The name/story id branch should then be deleted.

Note that, mostly depending on the language and the product, there might be some exceptions in the aforementioned workflow, but the PRs and Code Reviews will **always** be there. We embrace code reviews for a number of reasons:

* It helps devs to spot small issues that would've gone undetected without a
  review.
* It keeps the general knowledge of the projects shared between, at least,
  two people.
* It's a great way to spot and learn useful practices and to start defining
  guidelines.
* It allows automatic code-style checking to be performed by special tools,
  like elvis and houndCI.
* It keeps a nice and shinny git history that let us move back and forward in
  history and understand what happened and why during the course of the project development.

To get all the best from code reviews, while either submitting or performing a
code review, keep in mind the following points:

* Adopt a positive attitude!
* Try to evaluate the actual code (Is it easy to understand? is it maintanable?
  Are the right data structures being used? Are the variable and function/method names descriptive enough?, etc.) instead of the formatting. Ideally, the formatting should be validated by automatic tools, not by humans.
* As a reviewer, try to break your reviews into short sessions instead of one long time consuming ones. Also, try to have your own personal checklist of things to go over.
* As a submitter, keep your code short. The idea of a code review is to catch possible bugs, not show how much you can type in an hour.
* If your methodology is to collapse multiple stories into one PR, try to create at least one PR a day. Don't let your PRs grow over time, if you can avoid it.
* Don't forget to link PRs with issues by adding `[#ISSUE-ID]` to the PR description.
* You can easily reduce the burden of the whole workflow to just 3 commands using [AW](http://github.com/inaka/assisted_workflow).
* The blog post ["Effective Code Review"][effective-code-review] has a nice discussion of this topic.

---

## Project Documentation

All github projects are required to have a clear and useful README file on their root folder, so that it's properly displayed on github. Besides that, all products (i.e. applications, servers, etc.) should have a wiki in the associated github repository that must comply with our [wiki guidelines](WIKIS.md).

---

## Core Values

Below you can see the list of our main values. The ones we think are essential to our culture:

1. **Concentrate on the task at hand.**

    Focus on your tasks above all. Deliver on time, but never compromise
    quality. Follow the processes, but within reason (don’t create a detailed
    design and write a manual for a code review project, for example).

    Document as much as required, and keep your colleagues informed about the project experience (issues, problems and solutions, technical forums, progress reports, meeting minutes to log customer requests).

2. **Don’t complicate things, keep your design as simple as possible.**

    Make it work.

    Make it beautiful.

    Make it fast.

    In that order :)

3. **Respect your colleagues and customers.**

    Write code so that other people can read it with pleasure.

    Respect the coding conventions pertaining your language.

    Don't hide the problems, be honest.

    Be nice to people.

4. **Never break the master branch.**

5. **Version control your code** – Git is your friend.

6. **Do code review** – use pull requests.

7. **Build your code** – don't create a pull request without testing it first.

8. **Use the right tool for the job**

    When in doubt, prefer standard and proven tools over the last shouts of
    hipster fashion.

9. **Report the project’s progress.**

10. **Share your knowledge and experience, and learn from others.**

    Take notes on the wiki as you work. Share knowledge with your co-workers.
    Do post-project summaries. Write down stuff you have learned and make it
    publicly available.

---

## Communication

A lot has been said about roles, procedures, what to do, what not to do, etc.,
but sometimes even methodically following all of these guidelines is not enough
to ensure the positive outcome of a project. Most of what we've talked about
here can be easily fixed if problems arise. You can always move code back to a
working state, undo a commit, improve your estimates, etc., but what is very
difficult to fix are issues that arise from a lack of proper communication.

At the start of a project, things are usually fine, but as it advances, you
might end up losing track of what your responsibilities are or what the other
team members are up to. They are, of course, focused on their own tasks, but
with no communication between team members, it's easy to get lost in your own
little world and loose focus of the big picture. So, make sure you don't get too deep into your own tasks and forget about the other people. Try to keep track of what is being talked about in the chat room instead of just showing up when you're mentioned. Do your best to listen and demand to be listened to. Don't be afraid to talk to your teammates and let them know what the status of your work is, if you think you're not going to be able to deliver a task on time, etc.

This is not only valid for developers. The same goes for Project Managers. If
you can anticipate a storm is coming, don't wait for the rain to pour to let
the clients know. Golden rule is: Never keep users in the dark. Make a mental note to periodically send them a status update, so they're not only involved in the project, but they can also feel like they share ownership of it.

A successful project will most likely be defined by this item alone instead of
the actual bits and bytes.

[on-commit-messages]: http://who-t.blogspot.com/2009/12/on-commit-messages.html
[effective-code-review]: http://blog.fogcreek.com/effective-code-reviews-9-tips-from-a-converted-skeptic/
