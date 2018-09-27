# vistrails-tbwf
## Instructions for Running a Tuberculosis Workflow using VisTrails

Using data from the World Health Organization (WHO) on Tuberculosis, create a
workflow in VisTrails that reads in the data and computes the average
estimated incidence of tuberculosis per 100,000 people for a given country.

Docker containers referenced below are hosted on 
[Docker Hub](https://hub.docker.com):

  * Base container: https://hub.docker.com/r/scottsideleau/vistrails/
  * tb-wf containers: https://hub.docker.com/r/scottsideleau/tb-wf/tags/

The Dockerfile source for each of the containers is located in this repository.

  * vistrails: a Docker container with VisTrails installed
  * nigeria: a Docker container featuring the tb-wf:nigeria workflow
  * parameterized: a Docker container featuring the tb-wf:parameterized 
  workflow

You may choose to build any/all of the provided Docker containers by:

  1. Switching into any of the container source directories.

```bash
cd nigeria
```

  2. Issuing the Docker build command for the chosen container.

```bash
docker build -t tb-wf:nigeria .
```

A. View the generated workflow in VisTrails

  NOTE: These instructions assume a [MacOS](http://www.apple.com/macos/) 
  10.11+ environment with [Homebrew](http://brew.sh/index.html).

  1. Install [VisTrails](https://vistrails.org) on your local computer.

```bash
brew cask install vistrails
```

  2. Run VisTrails by selecting it from your Applications/ directory.

  3. Choose "File > Open" and select the include/a2.vt workflow.

  4. Choose the "nigeria-avg" workflow tag and click the "Execute" button.

B. Run the Nigeria workflow within a Docker container

  NOTE: These instructions assume a [MacOS](http://www.apple.com/macos/) 
  10.11+ environment with [Homebrew](http://brew.sh/index.html).

  1. Install [Docker](https://www.docker.com) on your local computer.

```bash
brew cask install docker
```

  2. Run Docker by selecting it from your Applications/ directory.

  3. Run the tb-wf:nigeria container and view results in STDOUT.

```bash
docker run scottsideleau/tb-wf:nigeria
```

C. Run the TB workflow with user-supplied country parameter in a Docker container

  1. Follow direction in (B, 1-2) to install and run Docker.

  2. Run the tb-wf:parameterized container and specify a country of interest.

```bash
docker run scottsideleau/tb-wf:parameterized country=Albania
```

  NOTE: The above example specifies Albania vice Nigeria, the latter of which 
  was chosen for the user in Part A above.  Experiment freely with other 
  country names.
