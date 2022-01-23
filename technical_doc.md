# Double Pendulum Technical Documentation

**Last updated:** 2022-01-23\
_Document generation aided by **Documatic**_

Automatic Documentation

* [Introduction](#introduction)
* [Code Overview](#code-overview)

## Introduction

This is a technical document detailing
        at a high-level
        what Double Pendulum does, how it operates,
        and how it is built.

The outline of this document was generated
        by **Documatic**.
<!---Documatic-section-group: arch-start--->


## Project Architecture


<!---Documatic-section-group: arch-end--->

<!---Documatic-section-group: helloworld-start--->


## Code Overview

The codebase has a flat structure, with 6 code files.
<!---Documatic-section-helloworld: setup-start--->

No exact compatable Python version has been detected.
Versions below 3.8 are compatable.

Install from pypi with `pip install main`.



<!---Documatic-section-helloworld: setup-end--->
`double_pendulum.simulation` has a `__main__` entrypoint, which calls:

* `double_pendulum.simulation.__run_basic_example`

`double_pendulum.animations` has a `__main__` entrypoint, which calls:

* `double_pendulum.animations.__run_basic_example`

`double_pendulum.RK_DAE_solver` has a `__main__` entrypoint, which calls:

* `double_pendulum.RK_DAE_solver.__run_basic_example`

`double_pendulum.pendulum` has a `__main__` entrypoint, which calls:

* `double_pendulum.pendulum.__run_basic_example`

`double_pendulum.tweet_it` has a `__main__` entrypoint, which calls:

* `double_pendulum.tweet_it.new_tweet`


<!---Documatic-section-helloworld: entrypoints-start--->


## Entrypoints

There are 0 source code entrypoints in top-level `__main__`/`__init__` files.


<!---Documatic-section-helloworld: entrypoints-end--->

<!---Documatic-section-group: concept-start--->
## Concepts
<!---Documatic-section-group: concept-end--->

<!---Documatic-section-group: helloworld-end--->

<!---Documatic-section-group: dev-start--->


## Developers
<!---Documatic-section-dev: setup-start--->





<!---Documatic-section-dev: setup-end--->

<!---Documatic-section-dev: ci-start--->
No CI/CD config files were detected.


<!---Documatic-section-dev: ci-end--->

<!---Documatic-section-group: dev-end--->
