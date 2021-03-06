# Rover Repos

## Overview

This package contains YAML files used to batch clone the repositories used on the lab rovers using [vcstool].

**Keywords:** vcstool, yaml, config

### License

The source code is released under a [GPLv3 license](https://www.gnu.org/licenses/gpl-3.0.en.html).

**Author: Miro Voellmy<br />
Affiliation: [European Space Agency](https://www.esa.int/)<br />
Maintainer: Miro Voellmy, miro.voellmy@esa.int**

The Rover Repos package has been tested under [ROS2] Foxy Fitzroy and Ubuntu 20.04. This is research code, expect that it changes often and any fitness for a particular purpose is disclaimed.

## Installation

### Building from Source

#### Dependencies

- [vcstool]

#### Building

This package doesn't need to be built. It can still be cloned into the ros2 workspace however:

	cd ros2_ws/src
	git clone https://github.com/esa-prl/rover_repos.git

## Usage


The files generated by [vcstool] store a list of repositories that can be batch cloned. The repositories can be exported/imported using the branch name (default) or using the specific commit hash (w/ `vcs export --exact`).

Branch versioning is used for initial setups while the exact versioning can be used to store and replicate very specific installations at a later time or on a different machine.

Files without a date contain **branched** exports.

Files with a date contain **exact** exports.

### Workspace Import - For Initial Setup

Make sure you are in your workspace:

`cd marta_ws/src`

And use vcs to automatically clone the repos specified in the *`*.yaml`* file.

`vcs import < ../../rover_repos/marta.repos`


### Workspace Export

Make sure you are in your workspace:

`cd marta_ws/src`

And use vcs to automatically clone the repos specified in the *`*.yaml`* file.

`vcs export > ../../rover_repos/marta.repos`

In order to freeze the exact state of a workspace (to save and recall the setup for a demonstration, to share and test a newly developed feature which requires checking different branches from different repos, etc.) the option `--exact` can be used. This saves the specific commit hash instead of the branch name, allowing the exact replication a workspace.

Add a descriptive name to the workspace to describe the contents of the file.

`vcs export > ../../rover_repos/marta_rover_openday_2020.repos --exact`

## Repo files


* **marta.repos** Contains repositories for the usage of the MaRTA pipeline in a simulation environment.

* **rock.repos** Contains rock dependencies for usage with old packages and drivers.


## Bugs & Feature Requests

Please report bugs and request features using the github issue tracker.

 
[ROS2]: http://www.ros.org
[vcstool]: https://github.com/dirk-thomas/vcstool
