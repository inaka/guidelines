![Inaka](http://inaka.net/assets/img/inaka-logo.png "Inaka")
## _…or how do we get stuff done around here_

 * [Introduction](#introduction)
 * [Workflow Styles](#worflow_styles)
 * [Starting Project](#starting_project)
  * [Description](#starting_project_description)
  * [Workflow](#starting_project_workflow)
 * [Solo Project](#solo_project)
  * [Description](#solo_project_description)
  * [Workflow](#solo_project_workflow)
 * [Team Project](#team_project)
  * [Description](#team_project_description)
  * [Workflow](#team_project_workflow)
 * [Client's Project](#client_project)
  * [Description](#client_project_description)
  * [Workflow](#client_project_workflow)
 * [Client's Project with Internal Testing](#client_project_2)
  * [Description](#client_project_2_description)
  * [Workflow](#client_project_2_workflow)
 * [Git Resources and Tips](#git_resources)
 * [GitHub Resources and Tips](#github_resources)

### <a id="introduction">Introduction</a>
This document describes the usual workflow for Inaka's projects.
It's meant to be followed by all developers and in every project at the firm.
If you're a dev and you find a project with something that doesn't quite fit in this workflow description, please contact [@elbrujohalcon](/elbrujohalcon) and improve this document together.

### <a id="worflow_styles">Workflow Styles</a>
There are various different project scenarios at Inaka. Each one has its own workflow described below. To know which one fits your current job best, check the following list:
* If your project is just starting, use the [Starting Project](#starting_project) workflow
* If you're the only developer using the repo (for instance, you're the only iOS dev in the project), use the [Solo Project](#solo_project)
* If you're working with other devs in a repo hosted at Inaka's github account, use the [Team Project](#team_project)
* If you're working in a project primarily hosted at the client's github account where the project testing is done at Inaka prior to submit changes to the client use the workflow that fits best (from the previous one) but adapt it according to the [Client's Project with Internal Testing](#client_project_2) workflow
* If you're working in a project primarily hosted at the client's github account use the workflow that fits best (from the previous one) but adapt it according to the [Client's Project](#client_project) workflow

### <a id="starting_project">Starting Project</a>
#### <a id="starting_project_description">Description</a>
When we are just starting a new project, we usually need a fast workflow that lets us build a feature on top of the previous one. In other words, waiting for code-review would block the developer because he needs the things he implemented in the previous feature in order to work on the new one.
For this kind of project we generally have:
* a github repo under inaka's account, e.g. http://github.com/inaka/the_project
* a hipchat room, e.g. "The Project"
* a pivotal project (e.g. "The Project") or a list of issues in github (e.g. http://github.com/inaka/the_project/issues)
* a freckle project, e.g. "The Project"
* a group of developers (or maybe just one, in this case it doesn't matter)

#### <a id="starting_project_workflow">Workflow</a>
Let's say you're _Bob_ and you just started working on _The Project_. You need to implement _The First Task_ which has #333 (either in Pivotal or Github issues) and _The Second Task_ which has #334.
This is what you should do…
+ Open the pivotal story / github issue _#333_ and read it carefully
    + if it's a piv story mark it as started by pressing the "Start" button
    + if you have further comments or you want to discuss this with the PM or whatever, go to _The Project_ hipchat room and talk
      **NOTE:** Don't do it in private, share your knowledge and your doubts, Bob! We're here to help you!
+ Go to your console and make sure you're up to date with the project
```bash
$ cd /path/to/the_project
# We're using "master" branch here as the integration branch, it's usually the case but not always.
# You should use the project's integration branch instead.
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git push
```

[But I want to ```git pull```!](#pull_vs_fetch_merge)

+ Create a branch named [username].brief.description.of.your.task (you can optionally include the story/issue number).
```bash
$ git checkout -b bob.333.this.task
$ git push --set-upstream origin bob.333.this.task
```
+ You should see a message on hipchat telling everybody you created that branch
    + if you don't see it, just tell them yourself :P

+ Do your magic :star2:.
    + Commit and push as often as you can (at least once a day)
    + Always include the story/issue number on your commits:
      ```bash
$ git add [the files you changed]
$ git commit -m "[#333] Added test cases for this new feature"
$ git push origin bob.333.this.task
      ```

+ Close the story/issue
    + If it came from a pivotal story, mark it as finished, pressing the "Finished" button
    + For github issues just add _"Closes #333"_ to your last commit description

+ Make sure you're up to date on your branch, and if not rebase (this applies only if you branched from ``master`` in the first place, check task #334 below if this is not the case).
```bash
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git checkout bob.333.this.task
$ git rebase master
$ git push -f
```

+ Go to github, open a pull request from _bob.333.this.task_ to _master_
    + Don't forget to reference the story/issue in the PR description
    + If you are allowed, assign the PR to somebody who can review your code (when in doubt, choose @elbrujohalcon)

+ Record your time in freckle, with the story/issue number, a brief description of what you did and some tags. (e.g. ``#333, server, v3.0, implemented this task``)

+ **While somebody reviews your PR**, start your next task over the one you've completed (**NOTE:** your new branch is **not** started from ``master`` but from your current one, this way you'll have all your recently implemented code available to work with)
```bash
$ git checkout -b bob.334.second.task
$ git push --set-upstream origin bob.334.second.task
```

+ You should see a message on hipchat telling everybody you created that branch
    + if you don't see it, just tell them yourself :P

+ Do your magic, again :star:.

+ Close the story/issue

+ Make sure you're up to date on your branch, and if not rebase **or merge**. Rebasing is not a requirement here because it can be tricky.
    + If you choose to rebase, you need to be careful to rebase each branch from the one it was opened from:
```bash
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git checkout bob.333.this.task
$ git rebase master
$ git checkout bob.334.second.task
$ git rebase bob.333.this.task
$ git push -f
```
    + If you choose to merge, you can simply do
```bash
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git checkout bob.334.second.task
$ git merge master
$ git push -f
```

+ In the meantime, your PR will be reviewed
    + If your PR needs some changes, discuss the issues with your reviewer and just implement them in your new branch, so the reviewer know that they will be fixed in the next PR and that he can merge this one
    + The reviewer will then merge your PR and you'll get a mail with a link where you can click a button to delete your branch.
        + **Press it!** (and feel the satisfaction and power only available to the bravest of us… …or not)
        + Update your repo and delete your local branch
```bash
$ git checkout master
$ git fetch origin --prune
$ git merge origin/master
$ git branch -d bob.333.this.task
$ git checkout bob.334.second.task
$ git merge master
$ git push
```

***

### <a id="solo_project">Solo Project</a>
#### <a id="solo_project_description">Description</a>
For this kind of project we generally have:
* a github repo under inaka's account, e.g. http://github.com/inaka/the_project
* a hipchat room, e.g. "The Project"
* a pivotal project (e.g. "The Project") or a list of issues in github (e.g. http://github.com/inaka/the_project/issues)
* a freckle project, e.g. "The Project"
* you (i.e. just one developer using the repo)

#### <a id="solo_project_workflow">Workflow</a>
Let's say you're _Bob_ and you are working on _The Project_. You need to implement _The First Task_ which has #333 (either in Pivotal or Github issues) and _The Second Task_ which has #334.
This is what you should do…
+ Open the pivotal story / github issue _#333_ and read it carefully
    + if it's a piv story mark it as started by pressing the "Start" button
    + if you have further comments or you want to discuss this with the PM or whatever, go to _The Project_ hipchat room and talk
      **NOTE:** Don't do it in private, share your knowledge and your doubts, Bob! We're here to help you!

[But I want to ```git pull```!](#pull_vs_fetch_merge)

+ Create a branch named [username].brief.description.of.your.task (you can optionally include the story/issue number).
```bash
$ git checkout -b bob.333.this.task
$ git push --set-upstream origin bob.333.this.task
```
+ You should see a message on hipchat telling everybody you created that branch
    + if you don't see it, just tell them yourself :P

+ Do your magic :star2:.
    + Commit and push as often as you can (at least once a day)
    + Always include the story/issue number on your commits:
      ```bash
$ git add [the files you changed]
$ git commit -m "[#333] Added test cases for this new feature"
$ git push origin bob.333.this.task
      ```

+ Close the story/issue
    + If it came from a pivotal story, mark it as finished, pressing the "Finished" button
    + For github issues just add _"Closes #333"_ to your last commit description

+ Go to github, open a pull request from _bob.333.this.task_ to _master_
    + Don't forget to reference the story/issue in the PR description
    + If you are allowed, assign the PR to somebody who can review your code (when in doubt, choose @elbrujohalcon)

+ Record your time in freckle, with the story/issue number, a brief description of what you did and some tags. (e.g. ``#333, server, v3.0, implemented this task``)

+ **While somebody reviews your PR**, start your next task over the one you've completed (**NOTE:** your new branch is **not** started from ``master`` but from your current one, this way you'll have all your recently implemented code available to work with)
```bash
$ git checkout -b bob.334.second.task
$ git push --set-upstream origin bob.334.second.task
```

+ You should see a message on hipchat telling everybody you created that branch
    + if you don't see it, just tell them yourself :P

+ Do your magic, again :star:.

+ Close the story/issue

+ In the meantime, your PR will be reviewed
    + If your PR needs some changes, discuss the issues with your reviewer and just implement them in your new branch, so the reviewer know that they will be fixed in the next PR and that he can merge this one
    + The reviewer will then merge your PR and you'll get a mail with a link where you can click a button to delete your branch.
        + **Press it!** (and feel the satisfaction and power only available to the bravest of us… …or not)
        + Update your repo and delete your local branch
```bash
$ git checkout master
$ git fetch origin --prune
$ git merge origin/master
$ git branch -d bob.333.this.task
$ git checkout bob.334.second.task
$ git merge master
$ git push
```

***

### <a id="team_project">Team Project</a>
#### <a id="team_project_description">Description</a>
For this kind of project we generally have:
* a github repo under inaka's account, e.g. http://github.com/inaka/the_project
* a hipchat room, e.g. "The Project"
* a pivotal project (e.g. "The Project") or a list of issues in github (e.g. http://github.com/inaka/the_project/issues)
* a freckle project, e.g. "The Project"
* a group of developers

#### <a id="team_project_workflow">Workflow</a>
Let's say you're _Bob_ and you work on _The Project_. You need to implement _The Task_ which has #333 (either in Pivotal or Github issues).
This is what you should do…
+ Open the pivotal story / github issue _#333_ and read it carefully
    + if it's a piv story mark it as started by pressing the "Start" button
    + if you have further comments or you want to discuss this with the PM or whatever, go to _The Project_ hipchat room and talk
      **NOTE:** Don't do it in private, share your knowledge and your doubts, Bob! We're here to help you!
+ Go to your console and make sure you're up to date with the project
```bash
$ cd /path/to/the_project
# We're using "master" branch here as the integration branch, it's usually the case but not always. 
# You should use the project's integration branch instead.
$ git checkout master 
$ git fetch origin  
$ git merge origin/master  
$ git push  
```

[But I want to ```git pull```!](#pull_vs_fetch_merge)

+ Create a branch named [username].brief.description.of.your.task (you can optionally include the story/issue number).
```bash
$ git checkout -b bob.333.this.task
$ git push --set-upstream origin bob.333.this.task
```
+ You should see a message on hipchat telling everybody you created that branch
    + if you don't see it, just tell them yourself :P

+ Do your magic :star2:.
    + Commit and push as often as you can (at least once a day)
    + Always include the story/issue number on your commits:
      ```bash
$ git add [the files you changed]
$ git commit -m "[#333] Added test cases for this new feature"
$ git push origin bob.333.this.task
      ```

+ Close the story/issue
    + If it came from a pivotal story, mark it as finished, pressing the "Finished" button
    + For github issues just add _"Closes #333"_ to your last commit description

+ Make sure you're up to date on your branch, and if not rebase
```bash
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git checkout bob.333.this.task
$ git rebase master
$ git push -f
```

+ Go to github, open a pull request from _bob.333.this.task_ to _master_
    + Don't forget to reference the story/issue in the PR description
    + If you are allowed, assign the PR to somebody who can review your code (when in doubt, choose @elbrujohalcon)

+ Record your time in freckle, with the story/issue number, a brief description of what you did and some tags. (e.g. ``#333, server, v3.0, implemented this task``)

+ Go back to master
```bash
$ git checkout master
```

+ Wait for the PR to be reviewed and merged or rejected
    + If your PR was rejected or you need to make some changes:
        + go back to your local branch:
```bash
$ git checkout bob.333.this.task
```
+ Do your magic again :star:
     + Make sure you're up to date on your branch, and if not rebase

```bash
$ git checkout master
$ git fetch origin
$ git merge origin/master
$ git checkout bob.333.this.task
$ git rebase master
$ git push -f
```
+ Let the reviewer know that you're done and he can review the PR again on hipchat
    + If your PR was accepted, you'll get a mail with a link where you can click a button to delete your branch.
        + **Press it!** (and feel the satisfaction and power only available to the bravest of us… …or not)
        + Update your repo and delete your local branch
```bash
$ git checkout master
$ git fetch origin --prune
$ git merge origin/master
$ git branch -d bob.333.this.task
$ git push
```

***

### <a id="client_project">Client's Project</a>
#### <a id="client_project_description">Description</a>
For this kind of project we generally have:
* a github repo under the client's account, e.g. http://github.com/client/the_project
* a fork of that repo under inaka's account, e.g. http://github.com/inaka/the_project
* a hipchat room, e.g. "The Project"
* a pivotal project (e.g. "The Project") or a list of issues in github (e.g. http://github.com/inaka/the_project/issues)
* a freckle project, e.g. "The Project"
* a group of developers

#### <a id="client_project_workflow">Workflow</a>
In this case you, _Bob_, work on _The Project_ for _The Client_ and you need to implement _This Task_ with id #333.

First of all, you should once add a remote repo in your project folder to track the client's repo:
```bash
$ git remote add upstream git@github.com:client/the_project.git
```
Then, you should follow your standard inaka workflow, but with the following modifications:
+ When you need to get your local files up to date, you fetch/merge from ``upstream`` instead of ``origin``:
```bash
$ cd /path/to/the_project
$ git checkout master # We're using "master" branch here as the integration branch, it's usually the case but not always. You should use the project's integration branch instead.
$ git fetch upstream
$ git merge upstream/master
$ git push
```
+ When you open a pull request you do it against **the client's** _master_ branch

***

### <a id="client_project_2">Client's Project with Internal Testing</a>
#### <a id="client_project_2_description">Description</a>
For this kind of project we generally have:
* a github repo under the client's account, e.g. http://github.com/client/the_project
* a fork of that repo under inaka's account, e.g. http://github.com/inaka/the_project
* a hipchat room, e.g. "The Project"
* a pivotal project (e.g. "The Project") or a list of issues in github (e.g. http://github.com/inaka/the_project/issues)
* a freckle project, e.g. "The Project"
* a group of developers
* a Project Manager

#### <a id="client_project_2_workflow">Workflow</a>
For this kind of workflow, you should follow your standard Inaka workflow (as written before). The main differences with those workflows happens after a group of features is merged into master and tested, as follows…

First of all, you should once add a remote repo in your project folder to track the client's repo:
```bash
$ git remote add upstream git@github.com:client/the_project.git
```

+ When your PM asks you to issue a PR for the client, you should first get your local files up to date, both from ``upstream`` and ``origin``:
```bash
$ cd /path/to/the_project
$ git checkout master
$ git fetch upstream
$ git merge upstream/master
$ git fetch origin
$ git merge origin/master
$ git push
```

+ Then, you create a new branch **just for the PR**
```bash
$ git checkout -b bob.PR.description
$ git push --set-upstream origin bob.PR.description
```

+ Go to github, open a pull request from _bob.PR.description_ to the client repo's _master_ (which is the default action suggested by github when you click the PR button)
    + If you can, put a reference to the stories/issues in the PR description
    + If you are allowed, assign the PR to somebody who can merge it

+ Wait for the PR to be reviewed and merged or rejected
    + If your PR was rejected or you need to make some changes
        + the PM should open new stories/issues for them
        + they should eventually get merged into ``master`` (following the usual workflows)
        + then, the PM will ask you to update the PR…
```bash
$ git fetch origin
$ git checkout master
$ git merge origin/master
$ git checkout bob.pr.description
$ git rebase master
$ git push -f --set-upstream
```
        + Let the client know that you're done and he can review the PR again
    + If your PR was merged, you'll get a mail with a link where you can click a button to delete your branch.
        + **Press it!** (and feel the satisfaction and power only available to the bravest of us… …or not)
        + Update your repo and delete your local branch
```bash
$ git checkout master
$ git fetch origin --prune
$ git branch -d bob.pr.description
```
------

### <a id="pull_vs_fetch_merge">What's the difference between pulling and fetch/merging?</a>

+ When you use pull, Git tries to automatically do your work for you. <b>It is context sensitive</b>, so Git will merge any pulled commits into the branch you are currently working in. ```pull``` <b>automatically</b> merges the commits without letting you review them first. If you don’t closely manage your branches you may run into frequent conflicts.

+ When you fetch, Git gathers any commits from the target branch that do not exist in your current branch and <b>stores them in your local repository</b>. However, <b>it does not merge them with your current branch</b>. This is particularly useful if you need to keep your repository up to date, but are working on something that might break if you update your files. To integrate the commits into your master branch, you use merge.

When you clone a repository you fetch the entire repository to your local host. This means that at that time you have an origin/master pointer to HEAD and master pointing to the same HEAD.

When you start working and do commits you advance the master pointer to HEAD + your commits. But the origin/master pointer is still pointing to what it was when you cloned.

+ If you do a "git fetch" it will just fetch all the changes in the remote repository and move the origin/master pointer to HEAD. Meanwhile your local branch master will keep pointing to where it has.

+ If you do a "git pull", it will do basically the same thing, but it will try to merge whatever you pulled into your master branch.

Source: http://stackoverflow.com/questions/292357/whats-the-difference-between-git-pull-and-git-fetch

------
### <a id="working_branches_commits">Working with branches and commits</a>

Here we are=>

```
c1-c2-c3-c4[master]
          `-[task1]
```
So that's our flowgraph... you've been working, coding, making some magic (`c1` - `c2` - `c3`). At `c4` commit you've decide to start a new story to address a new pivotal task. You worked hard on that and after some commits, you made the pull request to someone, so he can check your fresh-written code.

```
c1-c2-c3-c4[master]
          `-c5-c6[task1] (PR)
```
As you finished "task1", you took another task from pivotal and you noticed that is related to your previous work with "task1".
In fact you've "branch-ed" task1, and you started working with that.

```
c1-c2-c3-c4[master]
        `-c5-c6[task1]    {branch task 1}
        `-c7-c8[task2]    {branch task 2 from task 1}
```
From here we have several situation that might happen:

####1) Your code reviewer had merged task1 into Master before you finish your task2

That's how the repo looks like:
```
c1-c2-c3-c4-----------,-merge[master]
        `-c5-c6[task1]
                      `-c7-c8[task2]
```

So, before you keep working with your work, take some minutes and type these commands:
```bash
git checkout task2
git rebase master

git push -f origin task2   //this is to set our remote repo like the local one.
```
now the repo looks like this...
```
c1-c2-c3-c4-----------,-merge[master]
        `-c5-c6[task1]               `-c7-c8[task2]
```

#####NOTE:

Actually it looks like:
```
c1-c2-c3-c4-----------,-merge[master]
        `-c5-c6[task1]               `-c7.1-c8.1[task2]
```
where c7.1 copy of c7 but applied to merge instead of c6… and c8.1 is like c8 but playing on c7.1 instead of c7

####2) You finished task2 before your code reviewer has done the review.
Here in the PR of task 2, we should let the code reviewer know that the PR includes task1 and task2, so he knows what is merging, and he can do it both at a time.

The flow will look like this...
```
c1-c2-c3-c4----------------------------,-merge[master]
        `-c5-c6[task1]-c7.1-c8.1[task2]
```

####3) Now, we basically are done... but what happens if our code reviewer asks us to modify something on the code we push for task1?

```bash
git checkout task1
# make more magic on task1 code
git commit -m "[task1] I changed what my code reviewer asked me"
git push
```

our flowchart like this:
```
c1-c2-c3-c4[master]
        `-c5-c6-c9[task1]
               `c7-c8[task2]
```

So...what do we have to do now to continue working on task2? Simple! rebase task 2 to task 1!
```
c1-c2-c3-c4[master]
        `-c5-c6-c9[task1]
                         `c7.1-c8.1[task2]

```
```bash
git checkout task2
git rebase task1
git push -f origin task2  
```

### <a id="git_resources">Git Resources and Tips</a>

 * [The GIT bible, the PROGIT book](http://git-scm.com/book)
 * [gitref](http://gitref.org)
 * [gitready](http://gitready.com)

### <a id="github_resources">GitHub Resources and Tips</a>
 * You can reference commits in wikis, issues, and commits, using `[git_sha]` 
 * Reference issues in wikis, issues, and commits, using `#35`
 * Reference issues from other repositories: `username/project#issue`
 * Use [emojis](http://www.emoji-cheat-sheet.com/) in your commits and issues.
 * Be sure to checkout the Full [Markdown syntax](https://help.github.com/articles/github-flavored-markdown).
 * You can make PR from command line with [github-gem](https://github.com/defunkt/github-gem)
 * Read more about [pull requests](https://help.github.com/articles/using-pull-requests)
