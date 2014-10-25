# **Microbox**

### Congrats! You found the smallest docker images for distribution.


|image|size|versions|
|-----|--------|-----|
|[microbox/**redis**](https://registry.hub.docker.com/u/microbox/redis/)|7MB | `latest` `2.8.17` `2.8.16` `2.8.15` `2.8.14` `2.8.13` `2.8.12` `2.8.11` `2.8.10` `2.6.17`| 
|[microbox/**rethinkdb**](https://registry.hub.docker.com/u/microbox/rethinkdb/)|50MB |`latest` `1.15.1` `1.15.0`| 
|[microbox/**etcd**](https://registry.hub.docker.com/u/microbox/etcd/)|17MB |`latest` `0.4.6`| 
|[microbox/**dockerui**](https://registry.hub.docker.com/u/microbox/dockerui/)|16MB |`latest` `0.4.0`| 
|[microbox/**gogs**](https://registry.hub.docker.com/u/microbox/gogs/)|39MB |`latest` `0.5.6`| 


CLI images are coming soon.


### Known Issues

- [#8518](https://github.com/docker/docker/issues/8518) The automated build of Docker Hub will duoble the image size.
We are switching to manual build until Docker Hub resolve this issue.


### Usage


```bash
docker run --rm -ti microbox/redis:latest --help
```


```bash
docker run --rm -ti microbox/rethinkdb:latest --help
```

```bash
docker run --rm -ti microbox/etcd:latest --help
```

### Lanuch your first gogs server

```bash
docker run -d -p 22:22 -p 3000:3000 -v /data/gogs:/data microbox/gogs:latest --name gogs
```

### Manage docker in browser

```bash
docker run -d -p 9000:9000 -v /var/run/docker.sock:/docker.sock microbox/dockerui
```

Visit http://docker-ip:9000/ to see the WebUI for docker

### Why it's so small?
If you are using SSD, you will realized the size does matter. The images are build from official binaries or source code using buildroot. Then remove the unnecessary files e.g. compilers, head file, cli tools, documents, man, libs and replacing the whole OS with busybox.

The images are only include the essential files that is strictly required for that particular application. If say in Java words. The official image is JDK. Microbox is JRE.


### Don't ship your software with OS
Really, you shouldn't put the whole OS into the docker image at most of the time. Docker is using Linux [namespace (cgroup)](http://en.wikipedia.org/wiki/Cgroups) to isolate the processes. It's more like a process management tool. Most of the files are not required to run your application. You don't need include them when you ship your image as a service. If you want to see what's happen in the container, please use [nsenter](https://github.com/jpetazzo/nsenter) or `docker exec` in Docker 1.3.


### I want more **Microbox** images
Please vote [here](https://github.com/microbox/microbox.github.io/issues), we will add more images according to your suggestions.


### Links

- [Microbox](http://microbox.io/)
- [Docker](http://docker.io)
- [Busybox](http://busybox.net)
- [Buildroot](http://buildroot.uclibc.org)


