## Introduction
This is the list of things to check for every open-source project that we create.

## Usage
Each project should have a github repo with github issues enabled. As the main dev in that project, you should make sure to have the corresponding items from the lists below reported as issues there, and work on having them implemented/done before releasing the 1.0 version of your product.

## General Items
- [ ] It has a github repo
- [ ] It has a proper Apache2 LICENSE file.
- [ ] It's has a clear and useful README.md
- [ ] It's documented (with examples)
- [ ] It's tested.
- [ ] It's hooked to the [open-source hipchat room](http://inaka.net/hipchat)
- [ ] It has a link to the [open-source hipchat room](http://inaka.net/hipchat) in its README.
- [ ] It has a link to [inaka.github.io](http://inaka.github.io) in its README and/or landing page.

## Exhibition
- [ ] There is a blog post about it.
- [ ] It's shared on social networks.
- [ ] It's shared on reddit.
- [ ] It's shared on hacker news with a title like Show HN: description.

## For Libraries
- [ ] It provides a sample application.
- [ ] Examples of use are documented in the README or linked from there.

## For Erlang Projects
It follows the rules for our [Project Setup](ERLANG.md#project-setup)
- [ ] proper rebar.config
- [ ] rebar3 `compile`, `dialyzer`, `doc` and `ct` work with **no warnings**
- [ ] `deps` coming from hex.pm
- [ ] elvis.config up to date.
- [ ] Meta testing in place.
- [ ] proper data for hex.pm on app.src

## For Elixir Projects
It follows the rules for our [Project Setup](ELIXIR.md#project-setup)
- [ ] all default deps in hex.pm
- [ ] proper data for hex.pm on mix.exs
- [ ] travis.yml up to date.

## For Erlang/Elixir Projects
- [ ] It's checked with [Gadget](http://gadget.inakalabs.com)
- [ ] It's shared on [Erlang Central](http://erlangcentral.org/add-news/)
- [ ] It's published on [Hex.pm](https://hex.pm)

## For Ruby Projects
- [ ] It's checked with [Hound](https://houndci.com)

## For Swift Libraries
- [ ] It follows our [Swift open-source guidelines](https://github.com/inaka/swift_guidelines/wiki/Open-Source)

## For Node Projects
- [ ] It's checked with [Hound](https://houndci.com)
- [ ] It's published as an npm package.
