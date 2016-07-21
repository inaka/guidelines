# General Elixir Guidelines

## Table of Contents

1. [Coding Guidelines](#coding-guidelines)
1. [Build Tools](#build-tools)
1. [Test Coverage](#test-coverage)
1. [Documentation](#documentation)
1. [Project Setup](#project-setup)
  1. [Dependencies](#dependencies)
  1. [Data for hex.pm](#data-for-hexpm)
  1. [Travis.yml](#travisyml)
1. [Building and Releasing](#building-and-releasing)
  1. [Steps for New Releases / Version Bumps](#steps-for-new-releases--version-bumps)

## Coding Guidelines

Make sure you comply with [elixir style guide](https://github.com/rrrene/elixir-style-guide). In order to automate the style checking, install [Credo](https://github.com/rrrene/credo) and run it before creating a new Pull Request. If possible, always run credo with `strict` flag: `mix credo --strict`.
Another must-have is to enable [Credo CI](http://credo-staging.inakalabs.com/) to automatically check your updates in GitHub.

## Build Tools

Before pushing a new Pull Request, run your unit tests locally and never push them if something is not green. If the project is open-source, setup [Travis CI](https://travis-ci.org) to automatically run your unit tests after each new change. Remember to add a badge to your README file informing the build is passing.

## Test Coverage

Always aim at 100% code coverage for your tests.
Don't deliver your code unless it has at least 75% coverage.
For a deeper explanation, check [this blog post](http://inaka.net/blog/2015/02/24/test-exceptions/).
Install [excoveralls](https://github.com/parroty/excoveralls) in your project and check the coverage before pushing new changes. If it's open-source, make sure to setup up [coveralls.io](https://coveralls.io) and add the coverage badge to your README file.
When using Travis CI, you can ask it to trigger a code coverage task after a successful build (check [.travis.yml](#travisyml) example below).

## Documentation

Exported functions in all your modules and the modules themselves, specially for open-source projects, should be documented using `@moduledoc` and `@doc` comments. Remember to install [ex_doc](https://github.com/elixir-lang/ex_doc) and have a proper task to build the doc files when needed. For open-source projects, [Inch CI](https://inch-ci.org) can be of use to check the documentation coverage, and you can also integrate it with Travis CI (check [.travis.yml](#travisyml) example below).

## Project Setup

### Dependencies

All deps used in the `default` profile should use the packages in [hex.pm](http://hex.pm). For deps used in other profiles, etc. it's a _nice to have_, but not mandatory.
When possible, assign the project to [Hex Faktor](https://beta.hexfaktor.org) to be informed of out-of-date dependencies.

### Data for hex.pm

The project's `mix.exs` file should include hex.pm package and description attributes. For instance:

```elixir
  @version "2.1.0"

  def project do
    [
      app: :your_app,
      version: @version,
      ...
      # Hex
      description: description,
      package: package
    ]
  end

  defp description do
    """
    A short project description
    """
  end

  defp package do
    [
      maintainers: ["Inaka"],
      licenses: ["Apache 2.0"],
      links: %{"GitHub" => "https://github.com/inaka/your_app"},
      files: ~w(mix.exs README.md CHANGELOG.md lib),
      links: %{
        "GitHub"  => "https://github.com/inaka/your_app",
        "Docs"    => "http://hexdocs.pm/your_app/",
        "Blog"    => "http://inaka.net/blog/…", # If there is one
        "Example" => "https://github.com/inaka/your_app/tree/master/example"
      }
    ]
  end
```

### Travis.yml

Specially for open-source projects integrating open code checkers with Travis CI builds, the `.travis.yml` file in your project root folder should look similar to:

```yml
  language: elixir
  elixir:
    - 1.2.3
  otp_release:
    - 18.2.1
  env:
    - MIX_ENV=test
  script: mix coveralls.travis
  after_script:
    - mix deps.get --only docs
    - MIX_ENV=docs mix inch.report
```

## Building and Releasing

We use [hex.pm](https://hex.pm/) for open-source projects.

To generate the release you must update the version in your mix.exs and run:

``` bash
  $ mix hex.publish
```

### Steps for New Releases / Version Bumps

1. Increase the version number inside the project's `mix.exs` file.
2. In the project's root directory, execute the script:
`github_changelog_generator -t [YOUR_ACCESS_TOKEN] --future-release [NAME OF FUTURE RELEASE]`.
  * Install github_changelog_generator as a ruby gem: `$ gem install github_changelog_generator` 
  * If you don't have a GitHub access token already, create a [new one](https://github.com/settings/tokens).
3. Commit those changes and create a pull request to get them merged into `master`.
4. Create the new release in Github (this automatically creates the tag).
  * To do this, go to the project's home page, `Releases` and press the `Draft a new release` button.
  * Use `[NAME OF FUTURE RELEASE]` as its name.
  * Add `To see what's new check the [CHANGELOG](CHANGELOG.md)` as the change's description.
5. Optionally, publish the project to [hex.pm](http://hex.pm) using `mix hex.publish`
6. Update hex.pm docs for the project using `mix hex.docs`
7. :boom:
