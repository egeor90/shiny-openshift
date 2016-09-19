# Shiny Server Development Template

## Intoduction

This repo is intended to be forked and used as a development repo for R applicaitons that use shiny as a visualization server.  The code is designed
to run locally in development using Docker, and can be productionized using your github repo through OpenShift.

### Where do I put my code?

All of your code goes into the app directory. Data goes into the app/data directory and web resources such as css and images go into app/www directory.
If you have a README for your project, please also put it here.  Your shiny code can go into one file as per the example, or you can split it into
seperate ui and server files as you wish.

## Getting Started

There are several steps you must complete in order to begin:

### 1. Install Docker

Instructions for installing docker on your local OS are [provided here]("https://docs.docker.com/engine/installation/" "Yeah! Install Docker").

### 2. Fork this repo

This repo is already set up to work with Docker and Openshift, so it is simplest to fork this repo into your own, and thereby take advatage of any future changes to the tools provided.
Instructions for forking into your own github repo are [provided here]("https://help.github.com/articles/fork-a-repo/" "Fork Repo in Github").

### 3. Clone to your machine

You now need to clone the new repo onto your local machine so that you can start entering your code and developing.  There are many graphical tools available that can help manage this,
some of which can be found [here]("https://git-scm.com/download/gui/linux" "Github GUI").  Or you can simply use the command line, instructions for which can be
found [here]("https://git-scm.com/book/en/v2/Git-Basics-Getting-a-Git-Repository" "git command line").

### 4. Edit the packages.txt file

The packages.txt file contains an array of strings that indicate the packages you will will be using in your R program.  This list is used when building your local Dockerfile so that the
build process runs as fast as possible.  If you are familiar with Docker you know that you can also set environment variables that import this information, however this prevents the build process
from using the cached layer for this step.  Therefore the packages.txt file is used to build an explicit local Dockerfile that ensures fast repeated builds.

The packages.txt file should look something like this:
```
'package1', 'package2', 'package3'
```
with all packages on the same line.

### 5. Run / Develop