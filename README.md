# Docker Image: debian-systemd
[![Build Status](https://travis-ci.org/trly/debian-systemd.svg?branch=master)](https://travis-ci.org/trly/debian-systemd)

systemd enabled Debian Docker image built from the official Debian images

## Available Tags:
* buster
* buster-slim
* stretch
* stretch-slim
* jessie
* jessie-slim

## Using the image for [molecule](https://molecule.readthedocs.io/en/latest/) tests:

```
platforms:
  - name: debian-9
    image: trly/debian-systemd:stretch
    privileged: true
    command: /lib/systemd/systemd
```
