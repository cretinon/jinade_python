# jinade_python 

**jinade_python** is the python system for all [jinade projects](https://github.com/cretinon/jinade)

## Status
 projects  |  GitHub | Travis | debian_x86_64 | alpine_x86_64 | debian_armhf | alpine_armhf
 ------------  |  ------------ | ------------ | ------------ | ------------ | ------------ | ------------
[jinade_python](https://github.com/cretinon/jinade_python) | ![](https://img.shields.io/github/last-commit/cretinon/jinade_python.svg) | ![](https://travis-ci.org/cretinon/jinade_python.svg?branch=master) | ![](https://images.microbadger.com/badges/image/cretinon/jinade_python:debian_x86_64.svg)  | ![](https://images.microbadger.com/badges/image/cretinon/jinade_python:alpine_x86_64.svg) |  ![](https://images.microbadger.com/badges/image/cretinon/jinade_python:debian_armhf.svg) | ![](https://images.microbadger.com/badges/image/cretinon/jinade_python:alpine_armhf.svg)

Sources available on [Git Hub](https://github.com/cretinon/jinade_python) docker images available on [Docker Hub](https://hub.docker.com/r/cretinon/jinade_python/tags/) and build with [Travis-ci](https://travis-ci.org/cretinon/jinade_python)
makefile and .travis.yml inspire by [Whoahpython](https://github.com/woahpython/)

## Quick setup
### use these images
You can get theses images from dockerhub and use them directly.
Using one of the tag :
* alpine_armhf
* alpine_x86_64
* debian_armhf
* debian_x86_64
```
docker run -it --rm  --name jinade_python cretinon/jinade_python:YOURTAG sh
```
### build from sources
See development section. You'll have to clone then build then start
## Development
### clone
To clone this repository :
```
git clone https://github.com/cretinon/jinade_python.git
cd jinade_python
```
---
### makefile
---
#### variable

###### DISTRIB
You can choose your prefered distribution between
* debian
* alpine
###### ARCH
You can choose your prefered arch between
* x86_64
* armhf
---
#### command
##### build
build your image with specific DISTRIB and ARCH
```
make ARCH=x86_64 DISTRIB=debian build
```
---
##### start
run your container, detatch it and start service
```
make ARCH=x86_64 DISTRIB=debian start
```
---
##### shell
run your container, open a shell and do not start service
```
make ARCH=x86_64 DISTRIB=debian shell
```
---
##### logs
see your running container logs
```
make logs
```
---
##### rshell
open a remote shell, as root, inside your running container
```
make rshell
```
---
##### restart
restart your container
```
make restart
```
---
##### stop
stop your container
```
make stop
```
---
##### rm
remove your container (will stop it before)
```
make rm
```
---
##### clean
delete your container's image
```
make clean
```
---
##### all
build and start your container
```
make ARCH=x86_64 DISTRIB=debian all
```
---
##### travis specific commands
* pull
* push
* test
##### build specific commands
* regbinfmt
* fetch
* fetchqemu
---
##### new service / new project
Pre requisite :
* docker hub account
* github account
* travis account (need your travis token)
* modify current makefile in order to change usernames and email
In order to create a fresh environment for a new project :
```
make new_svc_pass new_svc_create NEW_SVC=python NEW_OPSYS=YOUR_OPSYS
# Enter DOCKER_PASS : changeme
# Enter GITHUB_PASS : whynot
# Enter TRAVIS_TOKEN : 123
cd ../YOUR_OPSYS_python/
make svc_first_push
```
---

![copyleft](https://upload.wikimedia.org/wikipedia/commons/c/c4/License_icon-copyleft-88x31.svg)
 [copyleft ](https://www.gnu.org/licenses/copyleft.html) licence
