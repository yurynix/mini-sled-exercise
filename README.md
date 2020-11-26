# We are the Sled team 🛷
We're an infrastructure team developing tools for all the FEDs at Wix.
Our main focus is sled, highly scalable, cloud based system to parallelize jest execution.

More about sled:

[![Sled case study](https://img.youtube.com/vi/hbz63Ve-eIY/0.jpg)](https://www.youtube.com/watch?v=hbz63Ve-eIY)

https://www.youtube.com/watch?v=hbz63Ve-eIY


# Exercise
The goal of this exercise is to learn&apply concepts to solve a loosely defined task.

In this exercise you will build a little demo of a "mini sled".
Just like the real sled, we'd like it to be built on top of [jest](https://github.com/facebook/jest) test runner.
You can learn on some of jest's architecture in this [video](https://www.youtube.com/watch?v=3YDiloj8_d0).

The end goal is to make jest tests execute on another computer instead of the computer that actually invokes jest (the computer that runs `npm test`).

In this repository, you can see a directory called `some-project`, this project have jest wired, and some tests
can be executed on jest via `npm test` (which is actually just invoking the `jest` command).

To mimick another computer, we'll use a docker container.

# Part 1
Create the facilities necessary to execute the spec files (one.spec.js, two.spec.js, etc.) on the running docker container instead of the "local machine".

You should **not** pre-load the spec files on the remote computer, we will test your solution on a different project than `some-project` with completely different spec files.

# Part 2
Create the facilities necessary to debug the remotely executed spec file.
Start by reading node's debugger [documentation](https://nodejs.org/en/docs/guides/debugging-getting-started/).
Please note: we don't want you to implement the UI of the debugger, use one of the existing clients.
For example, if the user (developer), wants to debug his spec file, the developer might execute:
```shell
DEBUG=true jest -f one.spec
```
A debugger would open and the developer would be able to step over/into the code in the spec file (in the example `one.spec.js`)

* Bonus: Make part 2 without exposing additional port(s) on the docker container, you can, however, create additional docker containers. This is to mimick that the "remote machine" and the "local machine" are both behind firewall(s), but still can access a 3rd machine, a "jump host".


# Initial setup
* Install docker, follow the instructions [here](https://docs.docker.com/get-docker/). [What is docker?](https://www.youtube.com/watch?v=JSLpG_spOBM)
* We've attached a Dockerfile, that is used to build a docker image from which you run a docker container that simulates the remote machine. At the moment it's a simple http server that returns `Hello world` when you issue a GET request to port 8080. You can and should change that application to complete the task.
* To build and run the docker container, follow README.md in the `remote-machine` directory.

## Before Submitting
* Make sure to use clean code. (References: [Clean Code: A Handbook of Agile Software Craftsmanship](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882), [Code Complete](https://www.amazon.com/Code-Complete-Practical-Handbook-Construction/dp/0735619670/) ). Make use of tools that will help you with standard [formatting](https://prettier.io/) an [linting](https://eslint.org/).
* You will be required to explain your implementation, make sure you understand all of your code.

## Submitting your project
After you've completed your tasks, and you are ready to submit it, do the following:
* Create a git repository (preferably on github.com)
* Make sure all the code is committed and pushed
* Make sure you added a markdown file (`README.md`) with instructions on how to run your project from scratch, that must include any operations that is required in order to run the project (i.e. setup a database, create tables, etc.)
* Clone your repo and use your instructions to see it works as expected
* Add `yurynix`, ???, and ??? as users to the repo (Master permission)
* Send us an email with your repo link


Good luck,

The sledders.

