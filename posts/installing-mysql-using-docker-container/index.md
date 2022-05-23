<!--
.. title: Installing Mysql using Docker container
.. slug: installing-mysql-using-docker-container
.. date: 2022-05-23 07:42:32 UTC+02:00
.. tags: docker, podman, mysql
.. category: 
.. link: 
.. description: 
.. type: text
-->

# Installing Mysql using Docker container

For my classes and my own learning I wanted to install mysql database. Mysql comes with dependencies and it's better to separate the database and isolate it from the environment. One of the best and most convenient ways of doing so is by using containers and Docker containers in particular.

So that's the goal, let's set up mysql on our system inside a Docker contaier and connect to it throgh software for managing databases like DBeaver or DataGrip.

And one more thing - I'm using podman as a CLI to install and manage Docker images. As long as you aren't using features like docker-swarm, podman's interface is 100% compatible with docker cli. So why podman? It's rootless (doesn't require root), also works better with Fedora/Red Hat, is less updated, doesn't require it's own repository etc. Since for my purposes podman and docker work the same I will use these terms interchangably but that does not apply to docker hub, because podman doesn't have it's hub and can use official Docker repository and other repositories.

Podman can use many docker image repositories, but I had the best luck with the docker.io repository.

## Installing podman

In Fedora just type:

    dnf install podman
    
In Debian/Ubuntu based distos run:

    apt-get -y install podman

For other distros visit: [podman installation](https://podman.io/getting-started/installation) .

## Running mysql image

Running a docker image actually does much more than running behind the scenes: it downloads the image if necessary, creates container based on the image and runs it based on the parameters given in the run command.

So let's discuss few parameters of the run command:
    




