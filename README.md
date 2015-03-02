# Supported tags and respective `Dockerfile` links
- [`0.0.0-master-branch`/Dockerfile](https://github.com/GELOG/docker-ubuntu-avocado/blob/0.0.0-master-branch/Dockerfile)

# What is Avocado ?
avocado is a distributed pipeline for calling variants, and is built on top of [Apache Spark](http://spark.apache.org/) and the [ADAM API](http://bdgenomics.org/projects/adam/). avocado provides a highly configurable pipeline that can be used for the alignment, processing, and variant calling of genomes/exomes/targets. We are currently in the process of hardening avocado for clincial use, and expanding the avocado pipeline so that it can triage processing steps based on genomic complexity.

avocado is on [Github](https://github.com/bigdatagenomics/avocado), and is in active development.

[http://bdgenomics.org/projects/avocado/](http://bdgenomics.org/projects/avocado/)

# What is Docker?
Docker is an open platform for developers and sysadmins to build, ship, and run distributed applications. Consisting of Docker Engine, a portable, lightweight runtime and packaging tool, and Docker Hub, a cloud service for sharing applications and automating workflows, Docker enables apps to be quickly assembled from components and eliminates the friction between development, QA, and production environments. As a result, IT can ship faster and run the same app, unchanged, on laptops, data center VMs, and any cloud.

[https://www.docker.com/whatisdocker/](https://www.docker.com/whatisdocker/)

## What is a Docker Image?
Docker images are the basis of containers. Images are read-only, while containers are writeable. Only the containers can be executed by the operating system.

[https://docs.docker.com/terms/image/](https://docs.docker.com/terms/image/)

# Dependencies
* [Install Docker](https://docs.docker.com/installation/)

# Base Docker image
* [gelog/spark:1.1.0-bin-hadoop2.3](https://registry.hub.docker.com/u/gelog/spark/)

# How to use this image?
### 1) Get the adam file of a genome (or chromosome) 
#### 1.1) Get it from [Adam](https://github.com/GELOG/docker-ubuntu-adam)

### 2) Get the reference genome (or chromosome) and unzip it. 
    mkdir /data/
    wget -O /data/chr1.fa.gz http://hgdownload.cse.ucsc.edu/goldenPath/hg19/chromosomes/chr1.fa.gz
    gzip -d /data/chr1.fa.gz
### 3) Find the variation of the genome (or chromosome) with Avocado
    docker run -ti --rm --name client-genomics -v /data:/data avo /bin/bash
    avocado-submit /data/SRR062634.adam /data/chr1.fa /data/SRR062634.avr /usr/local/avocado/avocado-sample-configs/basic.properties
