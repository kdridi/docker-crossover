# Supported tags and respective `Dockerfile` links

-	[`16.2.5-1` (*16.2.5-1/Dockerfile*)](https://github.com/kdridi/docker-crossover/blob/master/Dockerfile)

# Quick reference

-	**Where to get help**:  
	[the Docker Community Forums](https://forums.docker.com/), [the Docker Community Slack](https://blog.docker.com/2016/11/introducing-docker-community-directory-docker-community-slack/), or [Stack Overflow](https://stackoverflow.com/search?tab=newest&q=docker)

-	**Where to file issues**:  
	[https://github.com/kdridi/docker-crossover/issues](https://github.com/kdridi/docker-crossover/issues)

-	**Maintained by**:  
	[Karim DRIDI](https://github.com/kdridi/docker-crossover)

-	**Published image artifact details**:  
	[repo-info repo's `repos/crossover/` directory](https://github.com/kdridi/docker-crossover) ([history](https://github.com/kdridi/docker-crossover/commits/master))  
	(image metadata, transfer size, etc)

# What is CrossOver?

CrossOver is a Microsoft Windows compatibility layer available for macOS and Linux. This compatibility layer enables many Windows-based applications to run on macOS or Linux operating systems.

CrossOver is developed by CodeWeavers and based on Wine, an open-source Windows compatibility layer. CodeWeavers modifies the Wine source code, applies compatibility patches, adds configuration tools that are more user-friendly, automated installation scripts, and provides technical support. All changes made to the Wine source code are covered by the LGPL and publicly available.

> [wikipedia.org/wiki/CrossOver_(software)](https://en.wikipedia.org/wiki/CrossOver_(software))

![logo](https://upload.wikimedia.org/wikipedia/en/0/02/Cxlogo_linux.png)

# How to use this image

## start a X11 server

The X Window System (X11, or shortened to simply X) is a windowing system for bitmap displays, common on UNIX-like computer operating systems.

## configure X11 security

```console
ip=$(ifconfig en1 | grep inet | awk '$1=="inet" {print $2}')
xhost + $ip
```

## start the image

```console
docker run --rm -it -e DISPLAY=${ip}:0 kdridi/crossover
```