## Introduction
All Inaka's github main project repos (i.e. the repos containing the main
application code, not the library ones) are required to have a README file and a
wiki

## README file
Besides what's in the wiki, each project should have a README file in its root
folder with instructions on everything a dev will need to set up a development
environment and get the project working. If there is a way to generate
documentation from source code, it should be described there. The way to run the
system tests and check their coverage should be described there, too.

## Wiki Pages
Project wiki's should include **at least** the information listed below
(according to the kind of project the repo holds):

### General Pages
* **Guideline Exceptions**:
  - If the project is not exactly compliant with our [guidelines](README.md),
    there should a page in the wiki describing its deviations (including the
    reasoning behind them).

* **Design / Architecture**:
  - If there are some design or architecture graphics, there should a wiki page
    to hold them
  - Even if there are no graphics, but some design/architecture decisions are
    not evident from the code or the rest of the docs, there should be listed
    and described in the wiki

* **Account information**:
  - If the project requires facebook, twitter, linkedin, or just applications
    users for testing/support purposes, there should be a list of them (with
    their passwords) in the wiki.
  - If the project uses mixpanel, urban airship and/or flurry, the wiki should
    include the required users and passwords


### iOS Specific Pages
* **AppStore Information**, including dev account login and app name (individual
  identifier)


### Android Specific Pages
* **Google Play Information**, including account login, keystore and package
  name


### Server Specific Pages
* **Server Access Instructions**: Including lists of amazon servers, with
  descriptions and the required information to log into them using ssh.
  Or heroku app descriptions with names, users, passwords, etc.
* **Monitoring Info**: If the server is monitored by pingdom or other monitor
  system, this page should describe how to check/edit its configuration
* **Scale Testing**: A page stating the desired scale bounds, the current system
  bounds and the way to test them, including the instructions to set up a
  machine (or group of machines) to run the tests and how to interpret the
  results.
* **API Description**: If the server provides an API there should be a page
  (or more likely *some pages*) documenting it.
* **Expected API Usage**: If the server provides an API there should be a page
  describing how clients are supposed to use it, i.e. the expected workflow.
