# General Inaka Development Guidelines



## Introduction

This document describes the general guidelines we expect **all** our company
members (a.k.a. _inakos_) to comply with in all of our projects. For code
guidelines and best practices regarding specific languages please refer to the
corresponding `inaka/[language]_guidelines` github repo.



## Specific Guidelines for your Language

In this same repo we have 3 other guideline files, make sure you check the one
that applies to the language you're using:
* [iOS](IOS.md)
* [Android](ANDROID.md)
* [Erlang](ERLANG.md)



## Roles and Responsibilities in a Project

#### Developer

* Develops functional and non-functional features including tests and
  documentation as specified by the project stage and task description.
* Attends and actively participates in the daily stand-up and other meetings.
* Follows the guidelines regarding tools and applications that can be used in
  the project.
* Follows code conventions as defined in the corresponding guidelines document.
* Is responsible to raise warnings if unable to keep the deadlines on the
  assigned tasks, ensuring the project leader can take appropriate actions.
* Needs to notify immediately the Project Manager if an earlier estimate turns
  out to not be accurate.
* Is responsable to inform the Project Manager or techincal lead about any
  technical concerns regarding the project.
* Defines technical estimate of possible new projects.
* Keeps Pivotal updated over all tasks by properly setting the status of each
  task.
* Must track hours daily using the ticket ID in freckle. When creating an entry in freckle, a developer must add enough descriptive text so that the PM or Client will clearly understand where and on what specifically the time was spent. It should only be necessary to consult the pivotal or Jira # if further clarification is needed on the motives for this task. 
* Adds all important information/ logins needed for the project to the project
  wiki.
* Helps other team members with technical issues they may not be familiar with
  and passing on general and project-specific know-how.
* While consulting:
  * Notify the technical lead or project manager whenever something outside the 
    agreed scope of the project is requested by the client.
  * Always keep the client informed of holidays, sick days and vacations.
  * Keep the technical lead up to date on any technical decisions you had to
    make.
  * Get to know your coworkers, you are not a mercenary waiting to get out.
  * Do your best and be proactive, as @elbrujohalcon says, "remember you are the
    expert, make suggestions, improve things".
* Participates in the hipchat [daily](DAILY.md)

#### CTO and Technical Coordinators

* Coordinates and creates estimates for proposals.
* Defines the architectural and technical decisions, and makes them publicly
  available for all team members.
* Keeps all team members updated with any changes regarding the original
  technical decisions.
* Might act as a project manager.
* During the kickoff meeting, communicates initial design and goals of a project
  and main increments to the team. It is then up to the team and the lead to
  refine and extend the design and identify the tasks.
* Supervises the progress of tasks, ensuring they are implemented according to
  the agreed design and timeline as well verifying their quality.
* Solves blocking issues for the developers, and if necessary, escalates the
  problem with system administrators or technical coordinators.
* Identifies common patterns and new approaches to be reused in future projects.
* Puts team members with necessary know-how in contact.
* Sets up monthly meetings with developers in order to stay up to date with
  current events, problems, situations, etc.
* Participates in the hipchat [daily](DAILY.md)

#### Sales/ Management

* Handles the initial contact and discussions with the customers. Sets up and
  coordinates the assignment, including high level requirement collection,
  time/budget information and required level of service needed (e.g. proof of
  concept or complete product).
* Notifies the project manager about the start of the project, providing the
  technical customer contact info and the project plan (deliverables, deadline,
  agreed effort and mix of engineers/senior engineers).

#### Project Managers

* Is involved in reviewing the estimation and proposal documents for new
  projects.
* Needs to make sure that all project wikis are up to date.
* Informs all team members about important client decisions.
* Updates Pivotal always to reflect the latest scope of the project.
* Coordinates the work within the team.
* Is responsible for priorities and timelines in the project.
* Updates and documents regularly the project status and informs the client
* Needs to know about every customer interaction and has to assure the tone
  is always proper and that every request is handled appropriately.
* Follows the conventions as defined in the [guidelines document](https://docs.google.com/a/inakanetworks.com/document/d/1QaNdEa-_hcq6m-Jmn4xHlzxlqTmxmMv19V4JO58LQdI/edit)
* Makes sure before the project kick off to have all relevant materials
  available for the developers (required wireframes, assets, as well as our
  templated document describing the font sizes, typefaces, color palette, etc.
  You can view these documents here [here][styles-guidelines] and
  [here][styles-guidelines2]).
* Makes sure all necessary repos are set up before development start
* Makes sure the ops team sets up the required environments and our standard
  project tools for each project.
* Is responsible for relaying messages, improvements and suggestions between the
  developers and the client in an appropriate and clear way.
* Participates in the hipchat [daily](DAILY.md)

#### Operations

* Sets up all required environments and hardware for client projects (including
  web hooks for Hipchat).
* Needs to make sure all projects use the standard tools (e. g. Jenkins,
  logstash, pingdom, monit, etc.).
* Creates and maintains accounts on different platforms.
* Researches new ops solutions and possible improvements to our ops processes.
* Documents the project environment set up including deployment instructions for
  each project.
* Is in charge of maintaining running systems.
* Checks performance issues and, if needed, relays them to the appropriate
  developers and PMs.
* Keeps the inaka dashboard up and running with relevant information for the
  current projects.
* Collaborates with developers on deployment issues.
* Performs cost estimation for required services.
* Monitors all systems to prevent and detect operational problems.
* Is in charge of the office hardware
* Monitors and maintains the internal network.
* Is in charge of the initial setup of machines for employees.
* Keeps standards checklist for each project up to date.
* Creates memos for each ops/PM meeting and shares them with all participants.
* Participates in the hipchat [daily](DAILY.md)

#### QA

* Checks that a build is stable and not crashing before sending it to the client.
* Corroborates that delivered bugs or tasks are implemented as they were
  described in pivotal.
* Takes notes about build versions/numbers used for submitting.
* Makes sure that app is still working properly after client/server deploys
  or changes.
* Documents test results if required by PMs.
* Performs 'Update tests' once a new iOS release build is ready to be sent to
  the client.
* Participates in the hipchat [daily](DAILY.md)



## How to use Pivotal/ JIRA

#### For PMs

* Pivotal/ JIRA needs to get set up as detailed as possible. Separate UI from
  functional tasks. Do NOT just copy paste the tasks from the proposals. Add
  detailed descriptions and try to separate them so as to have each task as
  close to being one-day (or less) in duration as possible.
* Design/ UI tasks always need to have a screenshot attached in the task
* Milestones need to be added, as well Release Dates
* The Pivotal tasks shouldn't be used as sub tasks, we use them as checklists
  about the task.
* The client is not allowed to assign Pivotals to the developers directly. If
  the client has feedback/ rejections/ new issues he must assign the task to the
  PM. The PM must read it, check if all information the developer needs is
  there and if so then assign it to the developer. If not circle back with the
  client.
* Never mix different issues in one Pivotal. Close the original Pivotal and
  open a new one, if needed.
* Always label Pivotals (ios, android, server, admin, design, etc.).
* Check that the developers use Piv IDs and Jira IDs for time tracking.
* If there is missing information from the client, e.g. an API is still not
  final and no final documentation, do push back, do not assign the Pivotal to
  the developer. The developers should not work on it until at least the
  documentation is final.
* If there is a pivotal task that says "XXX is not working correctly", it should
  also include an explanation on how it should work. e.g. if the pivotal title
  is "The text in the title is right-aligned", the description or at least a
  comment in that pivotal should say something like "The text in the title
  should be centered".
* Add release lines indicating "above for QA", "above for PM" and "above for client". Tasks approved by QA need to be above the PM line and tasks ready for testing for the client need to be above for client line.
* Specify estimates on the pivotal story title.

#### For developers

* Pivotal/ JIRA must be always up to date and reflect what you are currently
  working on and what is next.
* Make sure you read the whole Ticket/Story and review attachments before you
  start working on them. If the tasks are not 100% clear to you reach out to the
  PM.
* Work in the order of the Pivotals. If you think a different order makes sense
  reach out to the Project Management for discussion and the PM then will update
  Pivotal.
* As soon as you start working on a task start the ticket.
* Don't deliver the task until it is testeable for the PM/ QA (either
  available on staging or the build is ready to test).
* For ios and Android: Add the build number as a comment when you deliver the
  task.
* If you leave a comment/ question in the Pivotal mention the person you need
  feedback from.
* If you find a bug, let your PM know and have them create a new task/story for
  it.



## TDD

We encourage the use of TDD as a method of development as much as it makes
sense. The reasons behind this approach are:

* As a developer, you must *never* submit code that's not tested (either with
  unit tests or otherwise). Therefore the time you would spend testing your
  changes manually, can also be spent writing an automated test for that same
  thing. That comes with the additional benefit that you can repeat that test
  as many times as you want and also get the other devs to automatically run it
  in every change, without actually having to remind and/or describe them how to
  test such a thing.
* Writing the tests before the actual code forces you to think about _what_
  your program should do before focusing on _how_ to achieve it. This leads to
  more accurate and, generally, simpler code.
* Having a good test coverage in your code base increases your general trust
  on the written code and allows for easier and safer refactoring if needed.
* If well written, tests usually works as documentation as well.

#### When to incorporate TDD
TDD is not suited for **all** scenarios, but there are some projects where it
**MUST** be used:
* If you're working on a API server project.
* If you're working on an open-source library.
* If your project involves UI work and your language has the proper tools to
  write tests for it (e.g. rspec).
* If you're writing an internal library with no UI pieces.



## Version Control

#### Github

* With only a few exceptions, all of our projects are hosted on Github under
  the Inaka organization account.
* When starting a new project, either for a client or an open source one, ask
  the CTO to create a new repository for you and give him a brief description as
  well as the main programming language under which the project will be
  developed.
* For a more detailed guide on how to use Github on your day to day taks, refer
  to the [Inaka Workflow](WORKFLOW.md).

#### Commit Messages

Good commit messages serve at least three important purposes:

* To speed up the reviewing process.
* To help us write a good release note.
* To help the future maintainers of the code (it could be you!), say five years
  into the future, to find out why a particular change was made to the code or
  why a specific feature was added.

The blog post ["On commit messages"][on-commit-messages] has a nice discussion
of commit messages.

Tip: if it seems difficult to summarize what your commit does, it may be because
it includes several logical changes or bug fixes, and are better split up into
several commits using `git add -p`.

#### Commit Rules

Check-in/push rules for the main repository/branch are the following:

* Code must compile – All code merged must **fully** compile. This should be
  true for all commits in the history, because if there are commits that don’t
  fully compile, it will be  more difficult to use git bisect. Partial commits
  with non-working code can be allowed if prior to submitting the pull request,
  the branch is rebased interactively and the partial commits squashed into a
  single commit. If desired, the work progress history can be retained in the
  extended commit message.



## Development Flow

In all of our projects (specially those hosted in our own github repositories)
we work with Pull Requests and Code Reviews. The process in a nutshell is:
* Grab a pivotal story/jira issue/github issue and mark it as started (e. g.
  let's say I want to work on piv `#123456` which is a piv story about editing
  this document).
* Open a branch with your name and the story id on it (e. g.
  `elbrujohalcon.123456.edit.this.document`). One or more commits per pivotal
  story, but no more than one pivotal id per commit.
* Tag all your commits with the story id
  (e. g. `git commit -m "[#123456] First edition"`).
* Once you're done, submit a Pull Request in github and assign it to a colleague
  of yours to review it (if none of them are available, assign it to your CTO).
  + While you wait for that review, you can pick a different task and start this
    process over. If the PR is a blocker, warn whoever is responsible to
    communicate your block.
* When opening a pull request to generate a page on which the changes can be
  discussed, make sure to have [WIP] at the beginning of the pull request title so
  that it is not merged. When the discussion concludes, change the title to
  remove [WIP] and notify the reviewer so they can merge the pull request.
* The reviewer will then write comments on the PR and you'll have the chance to
  discuss them and/or fix them.
* We also have automated tools (like [elvis](http://elvis.inakalabs.com)) that
  will review your code.
* When the review is done, your reviewer will merge your code into master.
* The branch should then be deleted.

Note that, mostly depending on the language and the product, there might be some
exceptions in the aforementioned workflow, but the PRs and Code Reviews will
**always** be there. We embrace code reviews for a number of reasons:
* It helps the devs spot small issues that would've gone undetected without a
  review.
* It keeps the general knowledge of the projects shared between, at least,
  two people.
* It's a great way to spot and learn useful practices and to start defining
  guidelines.
* It allows automatic code-style checking to be performed by special tools,
  like elvis and houndCI.
* It keeps a nice and shinny git history that let us move back and forward in
  history and understand what happened and why during the course of the projects
  development.

To get all the best from code reviews, while either submitting or performing a
code review, keep in mind the following points:
* Adopt a positive attitude!
* Try to evaluate the actual code (Is it easy to understand? is it maintanable?
  Are the right data structures being used? Are the variable and function/method
  names descriptive enough?, etc) instead of the formatting. Ideally the
  formatting should be validated by automatic tools, not by humans.
* As a reviewer, try to break your reviews into short sessions instead of one
  long time consuming session. Also, try to have your own personal checklist of
  things to check for.
* As a submitter, keep your code short. The idea of a code review is to catch
  possible bugs, not show how much you can type in an hour.
* If your methodology is to collapse multiple stories into one PR, try to create
  at least one PR a day. Don't let your PRs grow over time, if you can avoid it.
* Don't forget to link PRs with stories/issues/etc. by adding `[#PIV-ID]` to
  the PR description
* You can easily reduce the burden of the whole workflow to just 3 commands
  using [AW](http://github.com/inaka/assisted_workflow).
* The blog post ["Effective Code Review"][effective-code-review] has a nice
  discussion of this topic.



## Continuous Integration & Deploys

We use Jenkins in all our projects to automate testing, artefacts generation,
server configuration and deploys.

#### Continuous integration

* Mobile commits trigger
    * automatic builds.
    * builds shared by dropbox for testing.
    * automatic tests on each build.
    * coverage measurement.
    * coverage displayed on dashboard.

* Servers
    * automatic test.
    * coverage measurement.
    * coverage displayed on dashboard.

#### Server Configuration & Deploys

* Jenkins runs Ansible playbooks on target servers to set up the required
  configurations.
* New versions are deployed in servers using Ansible playbooks avoiding human
  errors during the process.
* When compilation of the code or artefacts generation is required we have a
  separate job in order to avoid losing time during deploys.

#### Tags and github releases

**Master:** Testeable versions of our products are merged with a pull request to
master. Then Jenkins can build the corresponding artifacts or deploy the the
server.

**Tags:** Once the version is fully tested in a safe environment and its ready
for release it is tagged as `production` and so that Jenkins can build and
deploy the same version.

**Releases:** After a deploy we tag the commit as a `release` with the date of
the deploy so that we can keep a clear history of what was working on production
at different dates.



## Time tracking

For tracking our hours, we use Freckle. Basically we use it to keep track of how
long we spent working on each task. There are several ways to track your time,
whichever you choose is up to you.

One of the ways is to use Freckle's own timer app to start/stop the timer every
time you start working on a new task, so that you know exactly how long you've
spent working on it. Another way is to simply keep track of the tasks you've
worked on during the day, and log them into Freckle at the end of the day.
Whichever way you choose, remember to always leave Freckle updated at the end of
the day.

When logging hours related to a specific project, they should be in the
following format: ``#PIV_ID, short description of the task``

For example: ``#4252514, Implemented Facebook SDK``

* Any time you spend working on tasks that are not related to any billable
  projects, like preparing for a presentation, working on an estimate, working
  on an open source project, etc. should be logged under the `Inaka Internal`
  project.
* Time **must** be entered daily, preferably throughout the day.
* Please divide your entries in tasks and try to track as exact as possible the
  time you spend on a task.
* Descriptions need to be clear and need to include a pivotal ID.
* Do not enter in one freckle entry several pivotal tasks. Divide them in
  several freckle entries so we know exactly how long each task took.
* Additionally, you need to add sick days and personal vacations into freckle.
  I. e. if you take a sick day, enter for that day 8 hours labelled "sick" under
  the `Inaka Internal` project. If you take vacations, for each vacation day
  enter 8 hours labelled "vacation" under the `Inaka Internal` project.
* For unpaid additional vacation you take (or days off) do the same, but the
  description instead of vacation use "unpaid off". The same concept applies to
  holidays, in which case we use "holiday" as the description.



## Project Documentation

All github projects are required to have a clear and useful README file on their
root folder, so that it's properly displayed on github.
Besides that, all products (i.e. applications, servers, etc.) that are developed
for a client (as opposed to internal products) should have a wiki in the
associated github repository that must comply with our
[wiki guidelines](WIKIS.md).



## Open source projects

Each developer has one day per month to spend on open source projects/ tasks.

* You can work alone or in a team.
* You can pick any already existing Inaka open source project or come up with a
  new idea.
* Check with the CTO if your idea is accepted.
* Make sure to let your PM know at least a few days before the day you want to
  use for open source so the PM can coordinate any project needs around it.
* When working on an open source project for Inaka, refer to the following
  document: ["Open Source checklist"][OPEN-SOURCE.md].



## Research and Resources

At Inaka, we encourage our devs to do research, learn and share knogledge as
much as possible. You're always welcome to learn new languages, paradigms,
technologies or even new programming concepts in general.

If you don't know where to start or if you want a fresh new book to read, check
[this impressively long list of free books](http://resrc.io/list/10/list-of-free-programming-books).
You can also suggest books and ask managment about paid books if you feel you
need them.

If you would like to purchase some resource, let our CTO or CEO know via email,
specifying all the pertinent details.

Also remember that Inaka has a public Dropbox
[folder](https://www.dropbox.com/sh/afv2cr0m50fdyy6/AACwdnfMiwK2NZMsGnvNfIdKa?dl=0)
with electronic versions of several books.



## Developer Values

1. **Concentrate on the task at hand.**

    Focus on your tasks above all. Deliver on time, but never compromise
    quality. Follow the processes but within reason (don’t create a detailed
    design and manual for a code review project for example).

    Document as much as required by the customer, and keep your colleagues and
    managers informed about the project experience (issues for problems and
    solutions, technical forums, progress reports, meeting minutes to log
    customer requests). Always try to solve the issues by talking if possible,
    and only log the outcome summary.

2. **Don’t complicate things, keep your design as simple as possible.**

    Make it work.

    Make it beautiful.

    Make it fast.

    In that order :)

3. **Respect your colleagues and customers.**

    Write code so that other people will read it with pleasure. Respect the
    coding conventions pertaining your language.

    Have the global `README.md` file explaining what your project does and how
    to run it.

    Don't hide the problems, be honest.

    Be nice to people.

    Friendly tip: before complaining about the ugliness or the state of mess of
    a code you're handed, do a `git blame` first to make sure you're not
    insulting anyone in the office. :)

4. **Never break the master branch.**

5. **Version control your code – Git is your friend.**

6. **Do code review – use pull requests.**

7. **Build your code – we have Jenkins as CI.**

8. **Use the right tool for the job**

    When in doubt prefer standard and proven tools over the last shouts of
    hipster fashion.

9. **Report the project’s progress.**

10. **Share your knowledge and experience and learn from others.**

    Take notes on the wiki as you work. Share knowledge with your co-workers.
    For example each project should have an overview wiki page. Do
    post-project summaries. Write down stuff you have learned and make it
    publicly available on the wiki.



## Communication

A lot has been said about roles, procedures, what to do, what not to do, etc,
but sometimes even methodically following all of these guidelines is not enough
to ensure the positive outcome of a project. Most of what we've talked about
here, can be easily fixed if problems arise. You can always move code back to a
working state, undo a commit, improve your estimates, etc, but what is very
difficult to fix are issues that arise from a lack of proper communication.

At the start of a project, things are usually fine, but as it advances, you
might end up losing track of what your responsibilities are or what the other
team members are up to. They are, of course, focused on their own tasks, but
with no communication between team members, it's easy to get lost in your own
little world and lose focus of the big picture. So make sure you don't get too
deep into your own tasks and forget about the other people. Try to keep track of
what is being talked about in the chat room, instead of just showing up when
you're mentioned. Do your best to listen and demand to be listened to in the
daily standups. Don't be afraid to talk to your PM and let them know what the
status of your work is, if you think you're not going to be able to deliver a
task on time, etc.

This is not only valid for developers. The same goes for project managers. If
you can anticipate a storm is coming, don't wait for the rain to pour to let
the clients know. Golden rule is: Never keep a client in the dark. Make a mental
note to periodically send them a status update, so they're not only involved in
the project, but they can  also feel like they share ownership of it.

A successful project will most likely be defined by this item alone instead of
the actual bits and bytes.

[on-commit-messages]: http://who-t.blogspot.com/2009/12/on-commit-messages.html
[effective-code-review]: http://blog.fogcreek.com/effective-code-reviews-9-tips-from-a-converted-skeptic/
[styles-guidelines]: https://docs.google.com/a/inakanetworks.com/spreadsheets/d/16PW-DJ_RlAQsUHcTVD2xqbY1ZMb10jSiZAQIYVl55xw/edit?usp=sharing
[styles-guidelines2]: https://docs.google.com/a/inakanetworks.com/document/d/1zqSOpyTaCayFX-P10NdC5VH18_-tTSQFNiCffiQoCt4/edit?usp=sharing
