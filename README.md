# What is Avocado ?
avocado is a distributed pipeline for calling variants, and is built on top of [Apache Spark](http://spark.apache.org/) and the [ADAM API](http://bdgenomics.org/projects/adam/). avocado provides a highly configurable pipeline that can be used for the alignment, processing, and variant calling of genomes/exomes/targets. We are currently in the process of hardening avocado for clincial use, and expanding the avocado pipeline so that it can triage processing steps based on genomic complexity.

avocado is on [Github](https://github.com/bigdatagenomics/avocado), and is in active development.

http://bdgenomics.org/projects/avocado/

# What is Docker?
Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications. Consisting of Docker Engine, a portable, lightweight runtime and packaging tool, and Docker Hub, a cloud service for sharing applications and automating workflows, Docker enables apps to be quickly assembled from components and eliminates the friction between development, QA, and production environments. As a result, IT can ship faster and run the same app, unchanged, on laptops, data center VMs, and any cloud.

https://www.docker.com/whatisdocker/

## What is a Docker Image?
In Docker terminology, a read-only Layer is called an image. An image never changes.

https://docs.docker.com/terms/image/

## what is a Docker Layer?
When Docker mounts the rootfs, it starts read-only, as in a traditional Linux boot, but then, instead of changing the file system to read-write mode, it takes advantage of a union mount to add a read-write file system over the read-only file system. In fact there may be multiple read-only file systems stacked on top of each other. We think of each one of these file systems as a layer.

https://docs.docker.com/terms/layer/

# Dependencies
* [Docker](https://docs.docker.com/installation/)
* Docker image of [gelog/spark:1.1.0-bin-hadoop2.3](https://registry.hub.docker.com/u/gelog/spark/)

# How to use this image?
```

```
