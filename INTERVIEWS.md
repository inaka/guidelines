![Inaka](http://inaka.net/assets/img/inaka-logo.png "Inaka")
## Interviewing Guidelines

### General

When interviewing candidates for whatever position, keep the following questions in mind:

* Why are they looking for a new job?
* Do they seem to be quick learners?
* Will they agree to do things the Inaka way (e.g. git, pivotal)?
* Do they understand the service business? Do they like working with clients?
* Do they have interests outside work?
* How is their written and spoken English? Are they at least in an intermediate level?

Ask them some of these questions:
* Can you describe a time when your work was criticized?
* Tell me about an important issue you encountered recently.
* Talk about something new you learned this month.
* What are you expecting from this firm in the future?
* Tell me about a time when you had to adapt to a difficult situation.
* What is your greatest achievement outside of work?
* Do you think you are overqualified for this position?
* Do you prefer to work independently or on a team?
* What techniques and tools do you use to keep yourself organized?
* What attracted you to this company?
* What type of work environment do you prefer?
* If you join a project where code is using tabs for identation but you prefer spaces, what would you do?

---

### Technical Positions

When interviewing candidates for technical positions, keep the following questions in mind:

* Are they passionate about programming?
* How is their overall attitude?  Are they easy to talk to?
  Do you think their personality will fit with the Inaka's team?
* Ask them to talk about their experiences in programming so far.
  What do they like/don't like?
* Can they show you any of the apps they developed?
  Can they explain the process?  The challenges?
* Do you see them capable of working independently on projects?
* Can they talk comfortably and with technical expertise about their past and
  current projects?
* Are they test-oriented? Do they understand test-driven and/or behaviour-driven
  development?

* Do they know how to use and understand git? Other source control management
  tools?
* Do they have github accounts?
* What are their recent open source contributions?
* Are they familiar with the command-line? Are they comfortable scripting or
  automating tasks?
* Do they understand the technologies involved in web development?
  * TCP/IP, HTTP, REST
  * JSON, character encodings
  * HTML, CSS, Browsers

For technical evaluations, you can:

* Ask the interviewee to pick an algorithm that the interviewer has already used and
  discuss it.
* See if they volunteer to test their code.
* Ask them to test the problem with good and bad data.
* Ask them to pick an open issue on one of the open source projects and solve it
  over the weekend.

---

### Questions to specific knowledge areas

#### Computer Science

* Do they know and understand the basic data structures?
* Do they know what a stable sort is?
* Do they understand what time and space complexity is, and can they estimate it for usual code?
* Do they understand operating system concepts such as memory, virtual memory, libraries, 
  linkers, multi-threading, resource management, stack vs heap?

#### Programming

* Can they do problem decomposition? i.e. Break up a problem into multiple functions,
  produce reusable code, encapsulate the aspects of the solution that are likely to change?
* Can they express/specify their ideas clearly?
* Do they organize their code well, both within and across source files?
* Is their code readable?
* Do they anticipate and handle error conditions, or do they implement defensive coding?
* Do they know their tools well? Do they develop their own tooling?
* Are they familiar with the common data modelling and database systems?
* Are they up to date with upcoming technologies?

#### Erlang Interview Questions

1. What is Erlang?
1. What are the key features of Erlang?
1. How are run-time errors handled in Erlang?
1. How are processes created?
1. Are you familiar with rebar3 or erlang.mk?
1. How do you deploy Erlang applications?
1. How do you _debug_ systems written in Erlang?
1. What problems is Erlang _not good_ at solving?

#### Ruby Interview Questions

1. What is a class, what is an object, and why do we need modules?
1. Ruby has open classes, could you explain what that means?
1. How can you get a Hash with ordered keys?
1. Is this a valid ruby code?

  ```ruby
  if user&.profile&.settings&.deliver?
    UserMailer.notify(user).deliver_later
  end
  ```

1. Have you already created and published a gem?

#### Ruby On Rails Interview Questions

1. How do you decide when to use `has_many through` or `has_and_belongs_to_many` in a model class?
1. How can we prevent using view helpers in order to have a more clear and object oriented solution?
1. How can you generate test data to run unit tests?
1. What's a good technique to improve tests where external API requests are required?

### General Frontend Interview Questions

1. Can you enumerate 3 ways to decrease page load time.
1. What does CORS stand for and what issue does it address?
1. Describe the difference between a cookie, sessionStorage and localStorage.

### Javascript Questions

1. What is a closure, and how/why would you use one?
1. What are the pros and cons of using Promises instead of Callbacks?
1. From the new features introduced by ES2015, what's the difference between using `var`, `let` and `const`?
1. Which javascript frameworks have you already used?

### AngularJS Questions

1. How do you organize the code inside your javascript folder for an AngularJS application?
1. Do you follow a styleguide or do you use a lint tool?
1. Can you explain what a directive is?
1. What is dependency injection and how does it work in AngularJS?
1. How can you implement routing in Angular?
1. Do you know what Karma and Protractor are?
1. What do you think about AngularJS 2? What about Typescript?

### BackboneJS Questions

1. What are the basic components provided by the Backbone framework?
1. How would you make a Backbone Collection deal with API responses when the response is not an array?
1. Why should we bind events using “listenTo()” instead of “on()”?

### Swift Questions
####Technical Questions
1. What's the difference between `viewDidLoad` and `viewDidAppear`? When would you use each?
1. What's the difference between a `let` and a `var` declaration? When would you use each?
1. What's the difference between a *value type* and a *reference type*? When would you use each?
1. What is a retain cycle?
1. What is the purpose of a `reuseIdentifier`? What is the main advantage of having it set?
1. What is an optional? What is an implicitly unwrapped optional? When would you use the former vs the latter vs a non-optional variable?
1. What is a protocol? When would you use it?
1. What is autolayout? What does it mean when a constraint is *broken*? Can you help me set up the constraints in the following view?
1. Have you ever worked with push notifications? Can you explain me what are the steps to receive push notifications?
1. **Final exercise:** 
  - We aim to evaluate:
    - Some of his/her git abilities (clone, branch, pull request)
    - His/her skills facing a random problem.
    - His work attitude overall.
  - For this, there are several options, among which these two are suggested:
    - Ask candidates whether their would like to solve an issue of some of our [Swift open source projects](https://inaka.github.io/). It's important to make it clear that this is **optional**. If so, suggest them to do it following the Inaka's git workflow. They can solve this after the interview, like a homework.
    - Otherwise, give them an exercise that they could solve in-place, during the interview.
  - Always have in mind the level of difficulty of the issue or exercise you choose, based on how they answered the technical questions.
  
####Experience Questions
1. What dependency managers do you know? Which one do you prefer, and why?
1. Which iOS-related frameworks have you worked with?
1. Have you ever heard of XMPP?
1. What's your experience dealing with provisioning profiles and code signing?
1. Have you ever made your own app and uploaded it to the App Store? If so, would you show it to me?

---

## General Check-List
At least in one of the interviews that we do with each candidate we need to assert the required
training period that will be needed if hired. To do that, run a ping-pong of questions with the
interviewee and check their level of expertise in our usual methodologies, practices, tools, etc.
As a bare minimum, check the items in the list below. For each one, if the candidate says that he/she has
experience on that, add a follow-up question to verify it. Examples are provided:
- [ ] git
  - [ ] Tell me about one git command that you know but not many people use regularly
- [ ] github / bitbucket
  - [ ] Show me an open-source repo to which you've contributed
- [ ] unix command line
  - [ ] What things do you do through command-line that you can't do with visual tools?
- [ ] code reviews / pull requests
  - [ ] What is in your mind the most important thing to keep in mind while reviewing code from others?
  - [ ] Have you used any automated code reviewer before (e.g. houndci, credoci, elvis, gadget, etc.)?
- [ ] Test-Driven Development
  - [ ] Do you write your tests before or after writing your code?
  - [ ] How often do you think it's worth it to invest time in analyzing and refactoring your code?
- [ ] Blog and/or Non-Technical Documentation Writing
  - [ ] If you have a blog, show me
  - [ ] If you have written non-technical docs for an open-source library, show me
  - [ ] Do you write in english or in your native language?
- [ ] Teaching
  - [ ] Have you given a course or only trained people individually?
  - [ ] What's the best number of students for a course in your opinion?
- [ ] Public Speaking
  - [ ] Do you have videos of your talks online?
- [ ] Pair Programming
  - [ ] How many hours should a pair programming session last for it to be worth it in your opinion?
  - [ ] What characteristics would you like you peer to have for your to pair program successfully?
- [ ] Pivotal / Jira / …
  - [ ] Have you ever had too many or too few tasks for a sprint? What did you do then?
- [ ] Freckle
  - [ ] If the interviewee used Freckle: Do you use the timer or enter all your hours at once?
  - [ ] If **never** used Freckle: By the end of each day, would you be capable of describing what you did on it?
- [ ] Estimates
  - [ ] Do you usually underestimate or overestimate tasks? How do you feel about that?
  - [ ] What was the hardest task for you to estimate?
