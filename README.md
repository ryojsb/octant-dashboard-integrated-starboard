# octant-dashboard-integrated-starboard
This Dashboard provides you with the observability integrated with starboard.

# Installation

## Prerequisit
Install starboard in your kubernetes cluster

https://github.com/aquasecurity/starboard

## Deploy octant

First, clone this repo.

```
# git clone https://github.com/ryojsb/octant-dashboard-integrated-starboard.git
# cd octant-dashboard-integrated-starboard/dockerfile
```

Then, you need to copy the config file it can connect to kubernetes cluster to this directory.
And it need to be named as `config`.

```
# ls
Dockerfile  config  octant_0.13.1_Linux-64bit.deb  starboard-octant-plugin  xdg-utils_1.1.2-1ubuntu2_all.deb
```

After that, build an image and push it to your registry.

```
# docker build -t <registry>/octant/gui:rev1 .

# docker login <registry>

# docker push <registry>/octant/gui:rev1
```

Finary, modify an image name in the manifest and apply it

```
# kubectl apply -f manifest/octant.yaml
```
