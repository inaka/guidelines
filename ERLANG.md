# General Erlang Guidelines

# THIS DOCUMENT IS WORK IN PROGRESS

##	Code Coverage
  **TODO:** 75% coverage

##	Code Checking tools
  **TODO:** xref, dialyzer, elvis, common_test

##	scale-testing
  **TODO:**: tsung / locust (Amilcar & Juan should come up with this one)

##	documentation
  **TODO:** (specially for open-source projects): edoc comments + erldocs
Code documentation should be in [EDoc format][edoc]. The general rules are the
following:

* **All exported functions** should have a **function specification and a decent
  description**. Any non-obvious side effect or anomalous behaviour
  should be documented in plain English as part of the EDoc documentation.
* All API functions should be fully documented, including everything above.
* Modules should be documented with the author’s name (as `John Doe
  <johnd@inaka.net>`).

  
##  Building and Releasing
  **TODO:** we use erlang.mk & relx (add process description and required files)
