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

Ask them:
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

### Questions to specific knowledge areas

#### Computer Science

* Do they know and understand the basic data structures?
* Do they know what a stable sort is?
* Do they understand what time and space complexity is, and can they estimate it for usual code?
* Do they understand operating system concepts such as memory, virtual memory, libraries, linkers, multi-threading, resource management, stack vs heap?

#### Programming

* Can they do problem decomposition? i.e. Break up a problem into multiple functions, produce reusable code, encapsulate the aspects of the solution that are likely to change?
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
1. What is the command to disconnect a node in Erlang?
1. To include a file in Erlang, what is the command used?
1. How are run-time errors handled in Erlang?
1. How are processes created?

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
