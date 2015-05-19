# General Erlang Guidelines

## Coding Guidelines
 Make sure you comply with our [coding guidelines](http://github.com/inaka/erlang_guidelines)

##	Code Coverage
 Always aim at 100% code coverage for your tests.
 Don't deliver your code unless it has at least 75% coverage.
 For a deeper explanation, check [this blog post](http://inaka.net/blog/2015/02/24/test-exceptions/)

##	Code Checking tools
 Check your code with all the available tools: xref, dialyzer and elvis. You can use [gadget](http://gadget.inakalabs.com) but don't just rely on it. Use the tools in your local environment as well.

##	scale-testing
 **TODO:**: tsung / locust (Amilcar & Juan should come up with this one)

##	documentation
 Exported functions in all your modules and the modules themselves, specially for open-source projects, should be documented using edoc comments. If possible, the project should provide a way to build the documentation in the Makefile using [erldocs](http://github.com/erldocs/erldocs)

##  Building and Releasing
  We use [erlang.mk](http://github.com/ninenines/erlang.mk) & relx. (Juan, Aki or Euen should iprove this one)

### Steps for New Releases / Version Bumps
   1. Increase the number version inside the project's `*.app.src` file.
   2. In the project's root directory execute the script:
      `github_changelog_generator -t [YOUR_ACCESS_TOKEN] --unreleased-label [NAME OF FUTURE RELEASE]`.
      * If you don't already have a GitHub access token, create a [new one](https://github.com/settings/tokens).
   3. Commit those changes and create a pull request to get them merged into `master`.
   4. Create the new release in Github.
      * To do this go to the project's home page, `Releases` and press the `Draft a new release` button.
      * Use `[NAME OF FUTURE RELEASE]` as its name
      * Add `To see what's new check the [CHANGELOG](CHANGELOG.md)` as the change description
   5. :boom:


