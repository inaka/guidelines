# General Inaka Development Guidelines



## Introduction

This document describes the general guidelines we expect **all** our company
members (a.k.a. _inakos_) to comply with in all of our projects. For code
guidelines and best practices regarding specific languages, please refer to the
corresponding `inaka/[language]_guidelines` github repo.



## Specific Guidelines for your Language

In this same repo we also have several other guideline files, specifically tailored to some languages or platforms (e.g. [iOS](IOS.md), [Android](ANDROID.md), [Erlang](ERLANG.md), [Elixir](ELIXIR.md), etc.). Check them out to find out how we work in those particular cases.

---

## Roles and Responsibilities (a.k.a. Career Path)
Below you'll find an outline of the technical roles and career paths available at Inaka. Career progression defines the process of moving on to better assignments with more responsibility. In each case, we will be leveraging the strengths of each employee, helping them make this progression through training, mentorship, self study and professional experience. At any one time, employees can take on multiple roles. For example, an Architect can also be a Technical Lead or a Project Manager. A Country Manager may also take on technical, training and project management roles. Responsibilities whilst working for us will include customer facing projects, developing end-to-end solutions, internal products, support, code and architecture reviews, research and training.

This career progression does not only depend on technical skills. While considering the role(s) each employee has in our company, we value technical, team player, communication and leadership skills altogether. Each role has its own requirements and therefore we provide alternative paths for those who thrive in the different areas.

Keep in mind that this list is not exhaustive, we have other roles, these are just the main ones.

#### Developer in Training
_Developers in Training_ are developers who are not ready to work independently on client projects or take on customer facing roles. That might be because they’re senior devs in other technologies and they’re learning a new one or because we specifically hired them considering their chances to learn any of the technologies we use on our projects. From being a developer in training, they can become _Developers_, _Senior Developers_ and _Architects_, depending on their previous experience.

A developer in training is expected to:

* Develop functional and non-functional features including tests and documentation as specified by the project stage and task description.
* Work for internal and/or open-source projects.
* Work on client projects but not in client-facing tasks.
* Be responsible to inform the Project Manager or Technical Lead about any technical concerns regarding the project.
* Work under close supervision of a Developer, Senior Developer or Tech Lead.

#### Developer
A developer will have the experience of designing and delivering multiple projects in at least one industry vertical. A Master’s degree with two years of experience, a Bachelor's degree with three to four years of experience or more if they do not have a degree. This is total developer experience we are counting, not expertise in a particular language. A Developer is expected to understand all the areas and tools related to the technology (e.g. code, unit tests, integration tests, releases, builds, scale testing, cross-browser testing, cross-device testing, integration with 3rd-party components, libraries, APIs, etc.) as well as any underlying frameworks and middleware of the respective languages or technology they are specialised in. They should master release handling and version control in a varied number of environments and operating systems. A developer should be able to perform some tasks under supervision and others on their own.

A developer is expected to:

* Develop functional and non-functional features including tests and documentation as specified by the project stage and task description.
* Write subsystem specifications which can be used by other developers.
* Work on client projects under the supervision of a Senior Developer.
* Work in internal and/or open-source projects.
* Take control and ownership of pieces of code created by other developers, even outside our company.
* Take responsibility for mentoring and coaching interns and graduate developers.
* Follow the guidelines regarding tools and applications that can be used in the projects.
* Follow code conventions as defined in the corresponding guidelines document.
* Be responsible to raise warnings if unable to keep the deadlines on the assigned tasks, ensuring the project leader can take appropriate actions.
* Be responsible to raise any concerns regarding implementations or specs as soon as they come up.
* Keep close communication with the project manager.
* Understand and be able to work with revision control software, software packaging and releases.
* Attend and actively participate in the [daily standup](DAILY.md) and other meetings.
* Follow the guidelines regarding tools and applications that should be used in the projects he works on.
* Follow code conventions as defined in the corresponding guidelines document.
* Keep project tracking tools updated by properly setting the status of each task.
* While consulting:
  * Notify the technical lead or project manager whenever something outside the agreed scope of the project is requested by the client.
  * Always keep the client informed of holidays, sick days and vacations.
  * Keep the Technical Lead up to date on any technical decisions.
  * Do their best to be proactive, as [@elbrujohalcon](https://github.com/elbrujohalcon) says: _"remember you are the expert, make suggestions, improve things"_.
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the Tech Lead
* While not assigned to a client project, work on Inaka open-source projects, the ESL internal TO-DO list, or write blog posts.

#### Senior Developer
A senior developer is someone with five to six years of experience working in client-facing projects in a variety of industries. They will have shown leadership abilities and are able to take responsibility for other Software Engineers within a project team. They have the ability to design, code, test and support software, starting the engagement with the projects in the estimation phase. This includes writing and executing research proposals and grant applications. A Senior Developer should be up to date in the most important matters of his area of expertise and should act as a reference for others in that field. They should have experience in implementing and understanding protocol stacks, data consistency models and the tradeoffs which need to be made between scalability and reliability. And also experience in supporting products, understanding the operational requirements needed by our customers.

Their role requires them to:

* Develop functional and non-functional features including tests and documentation as specified by the project stage and task description.
* Work in internal and/or open-source projects.
* Work for client projects unsupervised.
* Architect simple systems, such as 3-tier architectures or systems with heterogeneous nodes.
* Be able to analyze and assess the quality of code written by other devs, even those who do not work for our company.
* Supervise other team members on client and/or open-source projects.
* Follow and define the guidelines regarding tools and applications that can be used in each project.
* Follow and maintain code conventions and best practices for the corresponding language guidelines document that our company keeps.
* Inform the Project Manager or Technical Lead about any technical concerns regarding the project and help in finding proper solutions for them.
* Define technical estimates of possible new projects.
* Work with the Tech Lead in the definition of the architecture of projects.
* Help other team members with technical issues they may not be familiar with and passing on general and project-specific know-how.
* Help with recruitment and sales support.
* Attend and actively participate in the [daily standup](DAILY.md) and other meetings.
* Keep project tracking tools updated by properly setting the status of each task.
* While consulting:
  * Notify the technical lead or project manager whenever something outside the agreed scope of the project is requested by the client.
  * Always keep the client informed of holidays, sick days and vacations.
  * Keep the Technical Lead up to date on any technical decisions.
  * Do their best to be proactive, as [@elbrujohalcon](https://github.com/elbrujohalcon) says: _"remember you are the expert, make suggestions, improve things"_.
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the Tech Lead
* While not assigned to a client project, work on Inaka open-source projects, the ESL internal TO-DO list, or write blog posts.

#### Architect and Senior Architect
An Architect has over ten years (twenty for a senior architect) of experience, architected complex systems in a wide variety of verticals. They should be capable of making high-level design choices, dictate technical standards, including coding standards, tools, databases and platforms. They should be subject matter experts in their respective verticals and fields, having presented at conferences, published academic papers, articles or books.

Their role requires them to:

* Be able to architect scalable and resilient systems with no single point of failure.
* Understand the tradeoffs between Scalability and Availability in distributed systems.
* Be able to make choices between noSQL and SQL databases.
* Have good knowledge of consensus protocols, fallacies of distributed computing and the challenges involved in distributed systems.
* Ability to describe and get customer buy in for their solutions, both verbally and in writing.
* Be comfortable managing a team and customer relationships.
* Be comfortable with public speaking, writing articles and papers and training and mentoring other developers.
* Work in internal and/or open-source projects.
* Work for client projects unsupervised.
* Be able to analyze and assess the quality of code written by other devs, even those who do not work for our company.
* Supervise other team members on client and/or open-source projects.
* Follow and define the guidelines regarding tools and applications that can be used in each project.
* Follow and maintain code conventions and best practices for the corresponding language guidelines document that our company keeps.
* Inform the Project Manager or Technical Lead about any technical concerns regarding the project and help in finding proper solutions for them.
* Define technical estimates of possible new projects.
* Help other team members with technical issues they may not be familiar with and passing on general and project-specific know-how.
* Help with recruitment and sales support.
* Attend and actively participate in the [daily standup](DAILY.md) and other meetings.
* Keep project tracking tools updated by properly setting the status of each task.
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the Tech Lead
* While not assigned to a client project, work on Inaka open-source projects, the ESL internal TO-DO list, or write blog posts.

#### Technical Lead (or country CTO)
The CTO/Tech Lead is generally a senior developer or architect with proven capabilities for making high-level design choices, dictating technical standards and ensuring the quality of all products being built within the company regardless of the technology in which they’re developed. They are expected to be subject matter experts in at least one language and/or technology, having presented at conferences, published papers, articles or books.

They are responsible to:

* Work with the country managers, sales and/or project managers in the process of creating and reviewing estimates for potential clients.
* Define the company-wide architectural and technical standards and make them publicly available for all team members.
* Keep all team members updated with any changes regarding the original technical decisions.
* Have the ability to act as a project manager, if needed.
* During the kickoff meeting of each project, communicate initial design and goals of a project and main increments to the team.
* Supervise the progress of tasks, ensuring they are implemented according to the agreed design and timeline as well verifying their quality.
* Solve blocking issues for the developers, and if necessary, escalate the problem with system administrators or other technical coordinators.
* Identify common patterns and new approaches to be reused in future projects.
* Put team members with necessary know-how in contact.
* Speak with the local developers on a monthly basis staying on top of their challenges and providing any technical support they might need, or where necessary, acting as a door opener to other parts of the company.
* Participate in the [daily standup](DAILY.md)
* Coordinate open source projects.
* Stay on top of tooling, research and larger projects in the wider company, promoting them where applicable, in their local offices.
* Look for opportunities to cross promote toolings and other capabilities within the company.
* Set the recruitment standard in the various offices, and help with interviews.
* Help the sales teams with business development.
* Arrange tech days, hackathons and other activities aimed at promoting the personal development of the tech staff.
* Work with the country managers to decide what tasks to assign to staff on the bench.
* Work with the country managers and resourcing teams to decide who are the best developers to assign to each client job.

#### Project Managers
A project manager (Technical / non Technical) has the overall responsibility for the initiation, planning, design, execution, monitoring, controlling and closure of a project. A Technical Project Manager will use their technical background to further advance the project.

Responsibilities include:

* Being involved in reviewing the estimation and proposal documents for new projects.
* Work with sales on proposal creation.
* Make sure that all project documentation is up to date.
* Inform team members about important client decisions.
* Keep the scope of the project updated.
* Coordinate the work within the team.
* Be responsible for priorities and timelines in the project.
* Update and document the project status and inform the client regularly about it
* Know about every customer interaction and assure the tone is always proper and that every request is handled appropriately.
* Follows the PM conventions defined at Inaka.
* Make sure before the project kick off to have all relevant materials available for the developers.
* Make sure all necessary repos are set up before development start.
* Make sure the ops team sets up the required environments and our standard project tools for each project.
* Relay messages, improvements and suggestions between the developers and the client in an appropriate and clear way.
* Run project and sprint retrospectives and post mortems.
* Inform the country manager of any issues regarding projects or developers that the PM needs help on/ can't solve on its own.
* Participates in the [daily standup](DAILY.md)
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the CTO.

#### Operations
Our ops team is built by people who are in charge of all the hardware the developers and clients need. They are also in charge of monitoring and setting up servers and other components. Basically, all the operational and sysadmin related tasks that our projects include.

Their responsibilities:

* Set up all required environments and hardware for client projects.
* Ensure all projects use the standard tools.
* Create and maintain accounts on different platforms.
* Research new ops solutions and possible improvements to our ops processes.
* Document the project environment set up, including deployment instructions for each project.
* Be in charge of maintaining running systems.
* Check performance issues and, if needed, relay them to the appropriate developers and PMs.
* Collaborate with developers on deployment issues.
* Perform cost estimation for required services.
* Monitor all systems to prevent and detect operational problems.
* Be in charge of the office's hardware.
* Monitor and maintain the internal network.
* Be in charge of the initial setup of machines for employees.
* Keep standard checklists for each project up to date.
* Participate in the [daily standup](DAILY.md)
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the CTO.
* Maintain weekly meetings with all PMs and CTO to coordinate ops priorities.
* Create memos for each ops/PM meeting and share them with all participants.
* Write and maintain Internal Disaster Recovery Plan documentation for all projects.

#### QA
A QA team member is in charge of reviewing all of our systems before they reach the client hands. QA team provides warranties of functionality and usability for all the systems we build.

Their responsibilities are:

* Check that a build is stable and not crashing before sending it to the client.
* Corroborate that delivered bugs or tasks are implemented as they were described.
* Control build versions/numbers used for submitting.
* Make sure that each app is still working properly after client/server deploys or changes.
* Document test results if required by PMs.
* Perform 'Update tests' once a new client release build is ready to be sent to the client.
* Participate in the [daily standup](DAILY.md)
* Maintain [monthly meetings](MONTHLY-MEETINGS.md) with the CTO.
* Maintain weekly meetings with all PMs to discuss tasks for QA.
* Write test plans for each project after coordinating with the PM
* Do regular testing on projects that are in production while our company is still involved in

#### Country Manager
The position of Country Manager is not a position to which everyone will aspire. It does however provide a very significant move for the right person who sees that as being their chosen career direction. It offers a substantial level of autonomy and responsibility.

Responsibilities include:

* Be responsible for all aspects of the Company in that country. These duties may be undertaken via subordinates if the team size requires it:
    * Project delivery and customer satisfaction
    * Support the PMs and tech lead in their work
    * Budgeting, finance and accounting
    * Recruitment and Human Resources including team building and staff management
    * Health and Safety and office management.
    * Compliance with local laws.
* Be a member of the Company Senior Management team.
* Report to the CEO and liaise with others in Head Office as required.
* Represent the Company locally as required.

---

## How we use Pivotal/ JIRA

For project tracking we use [Pivotal](http://pivotaltracker.com) or [JIRA](https://www.atlassian.com/software/jira). Below you'll find our particular rules on how to use these systems.

#### For PMs

* Pivotal/ JIRA needs to be set up as detailed as possible. Separate UI from
  functional tasks. Do NOT just copy/paste the tasks from the proposals. Add
  detailed descriptions and try to separate them so as to have each task as
  close to being one-day (or less) in duration as possible.
* Design / UI tasks always need to have a screenshot attached in the task.
* Milestones need to be added, as well Release Dates.
* The Pivotal tasks shouldn't be used as sub tasks; we use them as checklists
  related to the main task.
* The client is not allowed to assign Pivotals to the developers directly. If
  the client has feedback/rejections/new issues, he must assign the task to the PM. The PM must read it, check if all information the developer needs is
  there and, if so, then assign it to the developer. If not, circle back with the client.
* Never mix different issues in one Pivotal. Close the original Pivotal and
  open a new one, if needed.
* Always label Pivotals (ios, android, server, admin, design, etc.).
* Check that the developers use Piv IDs and Jira IDs for time tracking.
* If there is missing information from the client, e.g. an API is still not
  final and there's no final documentation, do push back and do not assign the Pivotal to the developer. The developers should not work on it until at least the documentation is final.
* If there is a pivotal task that says "XXX is not working correctly", it should also include an explanation on how it should work, for example: if the pivotal title is "The text in the title is right-aligned", the description or at least a comment in that pivotal should say something like "The text in the title should be centered".
* Add release lines indicating "above for QA", "above for PM" and "above for client". Tasks approved by QA need to be above the PM line and tasks ready for the client to test need to be above the client's line.
* Specify estimates on the pivotal story title.
* Mark out of scope tasks as such.

#### For developers

* Pivotal/JIRA must be always up to date and reflect what you are currently
  working on and what is next.
* Make sure you read the whole Ticket/Story and review attachments before you
  start working on them. If the tasks are not 100% clear to you, reach out to the PM.
* Work in the order the Pivotals are listed. If you think a different order makes sense, reach out to the Project Manager for discussion, so that the PM can then update Pivotal.
* As soon as you start working on a task, start the ticket.
* Don't deliver the task until it is testeable for the PM/QA (either
  available on staging or the build is ready to test).
* For iOS and Android: Add the build number as a comment when you deliver the
  task.
* If you leave a comment or question in the Pivotal, mention the person you need feedback from.
* If you find a bug, let your PM know and have them create a new task/story for
  it.

---

## TDD

We encourage the use of TDD as a method of development as much as it makes
sense. The reasons behind this approach are:

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

#### When to incorporate TDD
TDD is not suited for **all** scenarios, but there are some projects where it
**MUST** be used:
* If you're working on an API server project.
* If you're working on an open-source library.
* If your project involves UI work and your language has the proper tools to
  write tests for it (e.g. rspec).
* If you're writing an internal library with no UI pieces.

---

## Version Control

#### Github

* With only a few exceptions, all of our projects are hosted on Github under
  Inaka's organization account.
* When starting a new project, either for a client or an open source one, ask
  the CTO to create a new repository for you and give him a brief description and the main programming language under which the project will be developed.
* For a more detailed guide on how to use Github on your day to day tasks, refer to this [Youtube Playlist](https://www.youtube.com/playlist?list=PL75bT2qMwxlWC9PsShtzOy5rBzYjSWPv7) by our CTO [@elbrujohalcon](https://github.com/elbrujohalcon).

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

We are an agile development shop. This means we tackle projects in an iterative
fashion (with each iteration called a sprint, which lasts one or two weeks in
duration) and show results early and often as we progress through a project.
With our clients, we set the priorities of each sprint so they are ultimately in control of the final outcome. Tools we most often use with our clients to aid with managing work and controlling source code are: pivotal, jira and github.

From a project day to day point of view, our developers work with Pull
Requests and Code Reviews. To any one of our developers, the process (in a
nutshell) is as follows:
* Grab a pivotal story/jira issue/github issue and mark it as started (e.g.
  let's say I want to work on piv `#123456` which is a piv story about editing
  this document).
* Open a branch with your name and the story id on it (e.g.
  `elbrujohalcon.123456.edit.this.document`).
* Tag all your commits with the story id
  (e.g. `git commit -m "[#123456] First edition"`).
* Remember you can have one or more commits per pivotal story,
  but no more than one pivotal id per commit.
* Once done, submit a Pull Request in github and assign it to a colleague
  so they may review it (if none are available, then assign it to your CTO).
  + While you wait for the review, you can pick a different task and start this
    process over. If the PR is a blocker, warn whoever is responsible to
    communicate your block.
* When opening a pull request to generate a page on which the changes can be
  discussed, make sure to have [WIP] at the beginning of the pull request title
  (or use the WIP label, if available) so that it is not merged. When the
  discussion concludes, change the title to remove [WIP] (or just remove the label)
  and notify the reviewer so they can merge the pull request.
* The reviewer will then write comments on the PR and you'll have the chance to
  discuss them and/or fix them.
* We also have automated tools (like [Elvis](http://elvis.inakalabs.com),
  [Credo](http://credoci.inakalabs.com), [Gadget](http://gadget.inakalabs.com) and
  [Hound](https://houndci.com/)) that will review your code and produce comments.
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
  history and understand what happened and why during the course of the projects
  development.

To get all the best from code reviews, while either submitting or performing a
code review, keep in mind the following points:
* Adopt a positive attitude!
* Try to evaluate the actual code (Is it easy to understand? is it maintanable?
  Are the right data structures being used? Are the variable and function/method
  names descriptive enough?, etc.) instead of the formatting. Ideally, the
  formatting should be validated by automatic tools, not by humans.
* As a reviewer, try to break your reviews into short sessions instead of one
  long time consuming ones. Also, try to have your own personal checklist of
  things to go over.
* As a submitter, keep your code short. The idea of a code review is to catch
  possible bugs, not show how much you can type in an hour.
* If your methodology is to collapse multiple stories into one PR, try to create
  at least one PR a day. Don't let your PRs grow over time, if you can avoid it.
* Don't forget to link PRs with stories/issues/etc. by adding `[#PIV-ID]` to
  the PR description.
* You can easily reduce the burden of the whole workflow to just 3 commands
  using [AW](http://github.com/inaka/assisted_workflow).
* The blog post ["Effective Code Review"][effective-code-review] has a nice
  discussion of this topic.

---

## Continuous Integration & Deploys

We use Jenkins and Ansible in all our projects to automate testing, and for artefacts generation, server configuration and deploys.

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
* When compilation of the code or artefacts generation is required, we have a
  separate job in order to avoid losing time during deploys.

#### Tags and github releases

**Master:** Testeable versions of our products are merged with a pull request to master. Then, Jenkins can build the corresponding artifacts or deploy to the
server.

**Tags:** Once the version is fully tested in a safe environment and its ready
for release, it is tagged as `production` so that Jenkins can build and
deploy the same version.

**Releases:** After a deploy, we tag the commit as a `release` with the date of
the deploy, so we can keep precise record of what was working on production
at different dates.

---

## Project Documentation

All github projects are required to have a clear and useful README file on their root folder, so that it's properly displayed on github.
Besides that, all products (i.e. applications, servers, etc.) that are developed for a client (as opposed to internal products) should have a wiki in the associated github repository that must comply with our [wiki guidelines](WIKIS.md).

---

## Talks & Conferences

As a developer, Inaka might give you the chance to speak at a conference.
If that's the case, these are the rules you have to follow for your presentation to be valid:

* You have to present a subject that's at least tangentially related to our work.
* You have to use the standard google slides template to build your slides.
* Before submitting your talk proposal, it has to be approved by the CTO and the CEO.
* Before presenting your talk, the slides and general content has to be approved by the CTO and the CEO.

---

## Open source projects

Each developer has one day per month to spend on open source projects/tasks.

* You can work alone or in a team.
* You can pick any already existing Inaka open source project or come up with a
  new idea.
* Check with the CTO if your idea is accepted.
* Make sure to let your PM know, at least a few days before the day you want to
  use for open source, so he/she can coordinate any project needs around it.
* When working on an open source project for Inaka, refer to the following
  document: ["Open Source checklist"](OPEN-SOURCE.md).
* In some occassions, it can be required to skip the open source day to ensure already agreed milestones and timelines with clients.

### Ownership vs. Authorship

Inaka will reserve the ownership of all open-source projects created by devs while working at the company. Therefore, while you can cite yourself as the author of a particular open-source project, it still has to be created under the inaka organization account in github and it has to be licensed under the Apache v2 LICENSE as specified in the [Open Source checklist](OPEN-SOURCE.md). The copyright portion in that license file should read:

```
   Copyright 2016 Erlang Solutions Ltd.
```

## Research and Resources

At Inaka, we encourage our devs to do research, learn and share knowledge as
much as possible. You're always welcome to learn new languages, paradigms,
technologies or even new programming concepts in general.

If you don't know where to start or if you want a fresh new book to read, check
[this impressively long list of free books](http://web.archive.org/web/20150503111059/http://resrc.io/list/10/list-of-free-programming-books/).
You can also suggest books and ask management about paid books if you feel you
need them.

If you would like to purchase some resource, let our CTO or CEO know via email,
specifying all the pertinent details.

---

## Core Values

Below you can see the list of our main values. The ones we think are essential to our company culture:

1. **Concentrate on the task at hand.**

    Focus on your tasks above all. Deliver on time, but never compromise
    quality. Follow the processes, but within reason (don’t create a detailed
    design and write a manual for a code review project, for example).

    Document as much as required by the customer, and keep your colleagues and
    managers informed about the project experience (issues, problems and
    solutions, technical forums, progress reports, meeting minutes to log
    customer requests). Always try to solve the issues by talking, and only
    log the outcome summary.

2. **Don’t complicate things, keep your design as simple as possible.**

    Make it work.

    Make it beautiful.

    Make it fast.

    In that order :)

3. **Respect your colleagues and customers.**

    Write code so that other people can read it with pleasure. Respect the
    coding conventions pertaining your language.

    Don't hide the problems, be honest.

    Be nice to people.

4. **Never break the master branch.**

5. **Version control your code** – Git is your friend.

6. **Do code review** – use pull requests.

7. **Build your code** – don't create a pull request it without testing it first.

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
little world and loose focus of the big picture. So, make sure you don't get too deep into your own tasks and forget about the other people. Try to keep track of what is being talked about in the chat room instead of just showing up when you're mentioned. Do your best to listen and demand to be listened to in the daily standups. Don't be afraid to talk to your PM and let them know what the status of your work is, if you think you're not going to be able to deliver a task on time, etc.

This is not only valid for developers. The same goes for Project Managers. If
you can anticipate a storm is coming, don't wait for the rain to pour to let
the clients know. Golden rule is: Never keep a client in the dark. Make a mental note to periodically send them a status update, so they're not only involved in the project, but they can also feel like they share ownership of it.

A successful project will most likely be defined by this item alone instead of
the actual bits and bytes.

[on-commit-messages]: http://who-t.blogspot.com/2009/12/on-commit-messages.html
[effective-code-review]: http://blog.fogcreek.com/effective-code-reviews-9-tips-from-a-converted-skeptic/
[styles-guidelines]: https://docs.google.com/a/inakanetworks.com/spreadsheets/d/16PW-DJ_RlAQsUHcTVD2xqbY1ZMb10jSiZAQIYVl55xw/edit?usp=sharing
[styles-guidelines2]: https://docs.google.com/a/inakanetworks.com/document/d/1zqSOpyTaCayFX-P10NdC5VH18_-tTSQFNiCffiQoCt4/edit?usp=sharing
