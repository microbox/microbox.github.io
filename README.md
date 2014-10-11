# **Microbox**

### Congrats. You found the smallest docker images

If you are using SSD, you will realized the size does matter. The images are build from official binaries or source code using buildroot. Then remove the unnecessary files e.g. document, man, libs and replacing the whole OS with busybox.

|image|size|versions|
|-----|--------|-----|
|microbox/**redis**|7MB | `latest` `2.8.17` `2.8.16` `2.8.15` `2.8.14` `2.8.13` `2.8.12` `2.8.11` `2.8.10` `2.6.17`| 
|microbox/**rethinkdb**|50MB |`latest` `1.15.1` `1.15.0`| 
|microbox/**etcd**|17MB |`latest` `0.4.6`| 


### Don't use docker like a Virtual Machine
Really, you shouldn't put the whole OS into the docker image at most of the time. Docker is using the Linux [namespace](http://en.wikipedia.org/wiki/Cgroups) to isolate the process. It's more like a process management tool. Most of the files are not required to run your application. if you want to see what's happen in the container, please use [nsenter](https://github.com/jpetazzo/nsenter).

### I want more **Microbox** images
Please vote [here](https://github.com/microbox/microbox.github.io/issues), we will add more images according to your suggestions.

### Links
[Docker](http://docker.io)

[Busybox](http://busybox.net)

[Buildroot](http://buildroot.uclibc.org)
