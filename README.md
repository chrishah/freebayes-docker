# freebayes-docker
Docker image for running freebayes in Ubuntu 18.04

The image contains a full install of [freebayes](https://github.com/ekg/freebayes), including all necessary dependencies. I am not part of the developer team - I just made this image.

In detail, the image is set up with:
 - Ubuntu 18.04
 - freebayes v1.2.0-10-g8a0dbee

To run freebayes you can do the following (this will mount the directory `/in` of the container to the current working directory on your local machine, and allow you to access files in this directory and any sub-directories):
```bash
$ docker run --rm -v $(pwd):/in -w /in chrishah/freebayes:v1.2.0-10-g8a0dbee freebayes -h
```

You can also enter the container environment and work within it. All executables should be in the `PATH`.
```bash
$ docker run -it --rm -v $(pwd):/in -w /in chrishah/freebayes:v1.2.0-10-g8a0dbee /bin/bash
```
