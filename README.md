# Tags
> _Built from [`quay.io/ibm/openjdk:11.0.8`](https://quay.io/repository/ibm/openjdk?tab=info)_
-	`6.7` - [![Build Status](https://travis-ci.com/lcarcaramo/docker-gradle.svg?branch=master)](https://travis-ci.com/lcarcaramo/docker-gradle)

### __[Original Source Code](https://github.com/keeganwitt/docker-gradle)__

Gradle

[Gradle](https://gradle.org/) is a build tool with a focus on build automation and support for multi-language development. If you are building, testing, publishing, and deploying software on any platform, Gradle offers a flexible model that can support the entire development lifecycle from compiling and packaging code to publishing web sites. Gradle has been designed to support build automation across multiple languages and platforms including Java, Scala, Android, C/C++, and Groovy, and is closely integrated with development tools and continuous integration servers including Eclipse, IntelliJ, and Jenkins.

![logo](https://raw.githubusercontent.com/docker-library/docs/c3d3ca6beed000f9ba6eabc98f3399158f520256/gradle/logo.png)

# How to use this image

## Building a Gradle project

* Create a Dockerfile that uses the Gradle base image to build your Gradle project.
```
FROM quay.io/ibm/gradle:6.7

WORKDIR /home/gradle/project
COPY . .

RUN chown -R gradle ../*

USER gradle

CMD [ "gradle", <gradle-task> ]
```
* Build the image.

`docker build . --tag <image name>`

* Run container using the image you just built.

`docker run --rm <name of image that performs gradle-task on your gradle project>`

Note the above container runs using uid/gid 1000 (user *gradle*) to avoid running as root. If you want to run the container as root, you can remove the lines in the above `Dockerfile` that handle assigning ownership and chaning users.

# License

View [license information](https://gradle.org/license/) for the software contained in this image.

As with all Docker images, these likely also contain other software which may be under other licenses (such as Bash, etc from the base distribution, along with any direct or indirect dependencies of the primary software being contained).

Some additional license information which was able to be auto-detected might be found in [the `repo-info` repository's `gradle/` directory](https://github.com/docker-library/repo-info/tree/master/repos/gradle).

As for any pre-built image usage, it is the image user's responsibility to ensure that any use of this image complies with any relevant licenses for all software contained within.
