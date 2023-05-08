# Automeda: A Generic CI/CD Solution

The general idea of this software will basically be to read the contents of
git repositories and to build, test, and eventually deploy the applications
once there are changes within that git repository.

This project will start off by having support strictly for Maven projects. It
will also have a main configuration file that contains the root paths to each
of the repositories, the hosts that they are deployed to, and whatever security
credentials we need to do SSH stuff on those hosts

This application is meant to be run on a "master" git server that would serve
as some companies main machine that accepts source code changes.

## Tags
#cicd #devops #java
