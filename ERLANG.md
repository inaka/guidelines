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
