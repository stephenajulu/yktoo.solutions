---
title: "Docker Indicator 0.1.0"
date: "2017-04-16T08:15:54+02:00"
description: >-
    I have developed a new application indicator to facilitate Docker container management.
tags:
    - containers
    - Docker
    - Docker Indicator
    - Python 3
    - software
    - software development
    - Ubuntu
    - Unity
    - Yakkety Yak
    - Zesty Zapus
categories:
    - software
author: "Dmitry Kann"
image: "indicator-docker-icon.png"
---

If you work with [Docker](https://www.docker.com/) a lot, you might have noticed that the list of containers tends to grow out of control over time. Now and then you bump into an abandoned dusty container somewhere in the dark corner of your `/var/lib`.

So I've created a  tiny so-called *application indicator* for **Ubuntu/Unity** to simplify managing my container collection. Please welcome the [Docker Indicator](https://github.com/yktoo/indicator-docker)!

<!--more-->

{{< imgfig "indicator-docker-icon.png" "Docker Indicator icon." >}}

## What is implemented so far {#features}

This is just an early beta that can still prove useful:

* The menu displays a live list of available containers (both running and stopped). The list is updated automatically thanks to Docker daemon event subscription.
* A container can be started or stopped by selecting the corresponding menu item.
* Whenever a container is started or stopped (not necessarily via the indicator), a desktop notification is shown.

Here's how it looks like:
{{< imgfig "indicator-screenshot.png" "Docker Indicator 0.1.0 screenshot." >}}

## Installation {#install}

This indicator is written on Python 3, just like the my other app, the Sound Switcher Indicator.

**Prerequisite:** you need to manually install [Docker Python API](https://github.com/docker/docker-py)—unfortunately the version available in Ubuntu's repos is fairly outdated. Installation in Ubuntu is pretty straightforward:

```bash
sudo pip3 install docker
```

The indicator can then be installed from [my PPA](https://launchpad.net/~yktooo/+archive/ubuntu/ppa):

```bash
sudo apt-add-repository ppa:yktooo/ppa
sudo apt update
sudo apt install indicator-docker
```

At this moment builds are available for *Ubuntu 16.10 Yakkety Yak* and *Ubuntu 17.04 Zesty Zapus*. The application is started automatically after login.

*By the way*, once I've started digging into the subject, I figured out that Docker has a great, fully [documented](https://docker-py.readthedocs.io/en/stable/) Python API, and also that the daemon is interacted with via REST calls to its web server. These calls can be monitored if you start the indicator with the `-vv` option. This is so awesome!

## Bug reports {#bug-reports}

Bug reports are welcome at the [GitHub issue tracker](https://github.com/yktoo/indicator-docker/issues). Please make sure you attach the console output provided by running:

```bash
indicator-docker -vv
```

## Source code {#source-code}

The complete source code is available in [my GitHub repository](https://github.com/yktoo/indicator-docker).

## To do {#to-do}

* Make a custom build of `python3-docker` so that you don't have to manually run `pip`.
* Add settings file.
* Add container remove function.
* Add Docker image management.
* … and lots of other stuff.

On a side note, the recent [announcement](https://insights.ubuntu.com/2017/04/05/growing-ubuntu-for-cloud-and-iot-rather-than-phone-and-convergence/) by Canonical that Unity will soon be discontinued makes the future of app indicators a bit uncertain…
