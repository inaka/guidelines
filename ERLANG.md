# General Erlang Guidelines

## Coding Guidelines

 Make sure you comply with our [coding guidelines](http://github.com/inaka/erlang_guidelines)

## Code Coverage

 Always aim at 100% code coverage for your tests.
 Don't deliver your code unless it has at least 75% coverage.
 For a deeper explanation, check [this blog post](http://inaka.net/blog/2015/02/24/test-exceptions/)

## Code Checking tools

 Check your code with all the available tools: xref, dialyzer and elvis. You can use [gadget](http://gadget.inakalabs.com) but don't just rely on it. Use the tools in your local environment as well.

## Documentation

 Exported functions in all your modules and the modules themselves, specially for open-source projects, should be documented using edoc comments.

## Project Setup

All erlang projects, specially open-source libraries, should comply to these rules:

### rebar.config

The project must use rebar3, for that, you will need a `rebar.config`.

The following lines are an example of `rebar.config`:

```erlang
%% -*- mode: erlang;erlang-indent-level: 2;indent-tabs-mode: nil -*-
%% ex: ts=4 sw=4 ft=erlang et

%% == Erlang Compiler ==

%% Erlang compiler options
{erl_opts,  [ warn_unused_vars
            , warn_export_all
            , warn_shadow_vars
            , warn_unused_import
            , warn_unused_function
            , warn_bif_clash
            , warn_unused_record
            , warn_deprecated_function
            , warn_obsolete_guard
            , strict_validation
            , warn_export_vars
            , warn_exported_vars
            , warn_missing_spec
            , warn_untyped_record
            , debug_info
         ]}.

{profiles, [
  {test, [
    {deps, [
      {test_dep, {git, "https://github.com/inaka/test_dep.git", {tag, "0.0.1"}}}
    ]}
  ]},
  {shell, [
    {deps, [
      %% Sync don't have releases so we use this stable version
      {sync, {git, "https://github.com/rustyio/sync.git", {ref, "9c78e7b"}}}
    ]}
  ]}
]}.

%% == Common Test ==

{ct_compile_opts, [ warn_unused_vars
                  , warn_export_all
                  , warn_shadow_vars
                  , warn_unused_import
                  , warn_unused_function
                  , warn_bif_clash
                  , warn_unused_record
                  , warn_deprecated_function
                  , warn_obsolete_guard
                  , strict_validation
                  , warn_export_vars
                  , warn_exported_vars
                  , warn_missing_spec
                  , warn_untyped_record
                  , debug_info
                 ]}.

{ct_opts, []}.

%% == Cover ==

{cover_enabled, true}.

{cover_opts, [verbose]}.

%% == Dependencies ==

{deps, [ sumo_db           % latest version of package
       , {zipper, "1.0.0"} % version 1.0.0 of a package
       ]}.

%% == Dialyzer ==

{dialyzer, [
    {warnings, [ unmatched_returns
               , error_handling
               ]},
    {get_warnings, true},
    {plt_apps, top_level_deps},
    {plt_extra_apps, []},
    {plt_location, local},
    {base_plt_apps, [stdlib, kernel]},
    {base_plt_location, global}
]}.

%% == Shell ==

{shell, [{apps, [sync]}]}.

```

For more information, you can check out the [official documentation](https://www.rebar3.org/docs/) or the [full example](https://github.com/erlang/rebar3/blob/master/rebar.config.sample).

### Dependencies

All deps used in the `default` profile should use the packages in [hex.pm](http://hex.pm). For deps used in other profiles, etc. it's a _nice to have_, but not mandatory.

### Elvis

The project should include an **updated** `elvis.config` file. Both `test` and `src` folders and their subfolders must be checked.

### Meta Testing

The project must include meta testing, using [katana-test](http://github.com/inaka/katana-test).
To do that, add these lines to `rebar.config`:

```erlang
{profiles, [
  {test, [
    {deps, [
      {katana_test, {git, "https://github.com/inaka/katana-test.git", {tag, "THE MOST RECENT VERSION"}}},
      {mixer,       {git, "https://github.com/inaka/mixer.git",       {tag, "THE MOST RECENT VERSION"}}}
    ]}
  ]}
]}.
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

And now, before we can run the `meta testing` suite, we need to generate the [`PLT`](http://erlang.org/doc/apps/dialyzer/dialyzer_chapter.html#id59082) (*required for Dialyzer test case*) using the following command:

``` bash
$ rebar3 dialyzer
```

Now you can run:

``` bash
$ rebar3 ct
```

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

## Building and Releasing

  We use [rebar3](http://www.rebar3.org/) & relx.

  To generate the release you have to run:

  ``` bash
  $ rebar3 release
  ```

### Steps for New Releases / Version Bumps

   1. Increase the version number inside the project's `*.app.src` file (this is not required if `vsn` is `git`).
   2. In the project's root directory, execute the script:
   `github_changelog_generator -t [YOUR_ACCESS_TOKEN] --future-release [NAME OF FUTURE RELEASE]`
   (`-u github_project_namespace -p github_project` might also be required).
      * If you don't have a GitHub access token already, create a [new one](https://github.com/settings/tokens).
      *Note*: the Installation instructions for `github_changelog_generator` can be found 
      [here](https://github.com/github-changelog-generator/github-changelog-generator#installation)
   3. Commit those changes and create a pull request to get them merged into `master`.
   4. Create the new release in Github (this automatically creates the tag).
      * To do this go to the project's home page, `Releases` and press the `Draft a new release` button.
      * Use `[NAME OF FUTURE RELEASE]` as its name.
      * Add `To see what's new check the [CHANGELOG](CHANGELOG.md)` as the change's description.
   5. Optionally, publish the project to [hex.pm](http://hex.pm) using `hexer`
   6. :boom:
