# Docker

A platform to build, share and run containers. <br>

## Docker Installation
We can use Docker Desktop for a friendly user interface where we can simple click and create containers. It can be installed from the docker website. <br>

As, we will usally be using docker in the linux machines, we can install docker using command line from the terminal. <br>
`sudo apt install docker.io` this simply installs docker but not all of docker. we can  install docker and all its dependencies from its offical website. <br>
The above command does installs the docker. However, the command varies with the operating systems. This command works only with the Debian based linux distros. the command for mac os and other distros will be a little bit different as they use different package manager.

`docker run -it --entrypoint=bash ubuntu` <br>This command runs a docker image in a container and to do that this first downloads the image from the dockerhub website and runs it inside the container.


# Virtual Machines
Docker is a virtual machine itself but we do need Virtual machines like for practicing locally and there is a difference. A VM lets you run a virtual machine on any hardware. Docker lets you run an application on any operating system.<br>

There are many types of virtual machines and there are different ones for different operating systems. some of the most popular ones are the `oracle virtual box` & `vmware`.<br>

We can download them from their official website: <br>
https://www.virtualbox.org/ <br>

https://www.vmware.com/ <br>

- After we Download those we can choose what machines to run. So, if we wanna run a ubuntu, <br> 
      - we downlad the iso image of ubuntu `https://ubuntu.com/download/server` <br>
      - use it inside the virtual box <br>
      - allocate recorces and network<br>
    we are good to go :) <br>

  - the same goes for any machines that we wanna use. <br>
