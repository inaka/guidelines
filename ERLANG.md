# General Erlang Guidelines

## Coding Guidelines
 Make sure you comply with our [coding guidelines](http://github.com/inaka/erlang_guidelines)

##	Code Coverage
 Always aim at 100% code coverage for your tests.
 Don't deliver your code unless it has at least 75% coverage.
 For a deeper explanation, check [this blog post](http://inaka.net/blog/2015/02/24/test-exceptions/)

##	Code Checking tools
 Check your code with all the available tools: xref, dialyzer and elvis. You can use [gadget](http://gadget.inakalabs.com) but don't just rely on it. Use the tools in your local environment as well.

##	Documentation
 Exported functions in all your modules and the modules themselves, specially for open-source projects, should be documented using edoc comments. If possible, the project should provide a way to build the documentation in the Makefile using [erldocs](http://github.com/erldocs/erldocs)

## Project Setup
All erlang projects, specially open-source libraries, should comply to these rules:

### Erlang.mk
The project must use the latest version of [erlang.mk](http://github.com/ninenines/erlang.mk).
To be sure you are using the latest version, grab any recently modern version of `erlang.mk` and run:
```bash
$ make erlang-mk
```

### Makefile
The following lines must be included in `Makefile`:
```Makefile
PROJECT = your_app

BUILD_DEPS = inaka_mk hexer_mk
DEP_PLUGINS = inaka_mk hexer_mk

include erlang.mk

ERLC_OPTS := +warn_unused_vars +warn_export_all +warn_shadow_vars +warn_unused_import +warn_unused_function
ERLC_OPTS += +warn_bif_clash +warn_unused_record +warn_deprecated_function +warn_obsolete_guard +strict_validation
ERLC_OPTS += +warn_export_vars +warn_exported_vars +warn_missing_spec +warn_untyped_record +debug_info
```

### Dependencies
All `DEPS` should use the packages in [hex.pm](http://hex.pm). For `SHELL_DEPS`, `TEST_DEPS`, etc. it's a _nice to have_, but not mandatory.

### Rebar
Adding `rebar.config` is optional, but if the project includes it, it must keep the deps versions and `erl_opts` in sync with `Makefile`

### Elvis
The project should include an updated `elvis.config` file. Both `test` and `src` folders and their subfolders must be checked.

### Meta Testing
The project must include meta testing, using [katana-test](http://github.com/inaka/katana-test).
To do that, add these lines to `Makefile`:

```Makefile
TEST_DEPS += katana mixer

dep_mixer = [[THE MOST RECENT VERSION]]
dep_katana = [[THE MOST RECENT VERSION]]
```

Then add a `your_app_meta_SUITE.erl` file to the project's `test` folder:

```erlang
-module(your_app_meta_SUITE).

-include_lib("mixer/include/mixer.hrl").
-mixin([{ktn_meta_SUITE
        , [ all/0
           , xref/1
           , dialyzer/1
           , elvis/1
          ]
        }]).

-export([init_per_suite/1]).

-type config() :: [{atom(), term()}].

-spec init_per_suite(config()) -> config().
init_per_suite(Config) -> [{application, your_app} | Config].
```

And now before we can run the `meta testing` suite we need to generate the [`PLT`](http://erlang.org/doc/apps/dialyzer/dialyzer_chapter.html#id59082) (*required for Dialyzer test case*) using the following command:

``` bash
$ make plt-all
```

**Note:** The rule for `plt-all` is within `inaka_mk` (previously added to `BUILD_DEPS` in the **Makefile** section).

### Data for hex.pm
The project's app.src file should include the following tuples:
```erlang
  {maintainers,["Inaka"]},
  {licenses,["Apache 2.0"]},
  {links,[ {"Github", "https://github.com/inaka/your_app"},
           {"Docs", "http://inaka.github.io/your_app/"}, % Unless you publish the docs directly on hex.pm
           {"Blog", "http://inaka.net/blog/…"}, % If there is one
           {"Example", "https://github.com/inaka/your_app/tree/master/example"} % If there is one
         ]},
  {build_tools,["erlang.mk"]}
```

##  Building and Releasing
  We use [erlang.mk](http://github.com/ninenines/erlang.mk) & relx.

### Steps for New Releases / Version Bumps
   1. Increase the number version inside the project's `*.app.src` file.
   2. In the project's root directory execute the script:
   `github_changelog_generator -t [YOUR_ACCESS_TOKEN] --future-release [NAME OF FUTURE RELEASE]`.
      * If you don't have a GitHub access token already, create a [new one](https://github.com/settings/tokens).
   3. Commit those changes and create a pull request to get them merged into `master`.
   4. Tag the commit in master with the new version.
   5. Create the new release in Github.
      * To do this go to the project's home page, `Releases` and press the `Draft a new release` button.
      * Use `[NAME OF FUTURE RELEASE]` as its name
      * Add `To see what's new check the [CHANGELOG](CHANGELOG.md)` as the change description
   6. optionally publish the project to [hex.pm](http://hex.pm) using `hexer`
   7. :boom:
