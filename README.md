![Double pendulum](double_pendulum.png)


The code behind [@pendulum_bot](https://twitter.com/pendulum_bot) Twitter bot which posts animations of a double pendulum released from a random position to swing for 30 seconds.


&nbsp;


# Basic usage

To create an animation of a random double pendulum:

```python
>>> from simulation import create_random_example, simulate
>>> from animations import single_animation
>>> rand_ex = create_random_example()
>>> results = simulate(rand_ex)
>>> single_animation(results, rand_ex)
```

The animation is saved as .mp4 video in `animations` subdirectory.

---

To create an animation and post it on Twitter, a valid API key is needed, and should be stored in `api_key.txt`.

```python
>>> from tweet_it import new_tweet
>>> new_tweet() # creates a new animation of random double pendulum
# or
>>> new_tweet('existing_file', 'My custom Twitter status')
```

---

To create double pendulum with the exact values for initial conditions:

```python
>>> from pendulum import Pendulum, DoublePendulum
>>> p1 = Pendulum(m=2.7, x=2.5, y=3.7, u=0, v=0)
>>> p2 = Pendulum(m=3.1, x=0.2, y=6.3, u=0, v=0)
>>> dp = DoublePendulum(p1, p2)
```

---

To create multiple pendulums with slight perturbations of initial conditions to observe chaotic behaviour:

```python
>>> from simulation import create_random_example, create_perturbations, simulate_multiple_examples
>>> from animations import multi_animation
>>> rand_ex = create_random_example()
>>> perturbed = create_perturbations(10, rand_ex, amount=1e-5)
>>> results = simulate_multiple_examples(perturbed)
>>> multi_animation(results, rand_ex)
```


&nbsp;


# Installation

```
git clone https://github.com/narimiran/double_pendulum.git
cd double_pendulum
```

### Dependencies

* Python 3
* numpy (running simulations)
* matplotlib (creating animations)
* ffmpeg or avconv/libavtools (saving videos)
* twython (posting Twitter updates)


&nbsp;


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


# FAQ

Q: *Why do you use Cartesian coordinates? I prefer polar coordinates.*

A: The initial task I was given was to implement double pendulum as DAE system in Cartesian coordinates. The idea for animations and Twitter bot came later, and Cartesian coordinates remained.

Q: *Which Runge-Kutta methods can I use?*

A: Any of these:

* Forward Euler (`Euler`)
* Explicit midpoint (`ExplicitMidpoint`)
* Ralston's method (`Ralston`)
* Kutta's 3rd order method (`Kutta3`)
* *the* Runge-Kutta 4th order method (`RK4`)
* Runge-Kutta-Fehlberg (`RKF`)
* Cash-Karp (`Cash-Karp`)
* Dormand-Prince method (`DOPRI5`)

Q: *Why can't I use implicit Runge-Kutta methods?*

A: Implicit methods require different solving method (solving a system of non-linear equations). This is not (yet) implemented.

Q: *Is there any damping/friction?*

There is no damping and no friction. The only force acting on the system is gravity.

Q: *Couldn't all/some of this be done simpler?*

A: Probably.


&nbsp;


# License

[MIT License](LICENSE.txt)