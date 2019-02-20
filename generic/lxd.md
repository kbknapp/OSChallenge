# Initialize LXD/LXC

```
$ sudo lxd init
```

# Copy Image Locally

Example, Ubuntu 18.04:

```
$ lxc image copy ubuntu:18.04 local: --alias ubuntu/18.04
```

Example, CentOS 7:

```
$ lxc image copy images:centos/7 local: --alias centos/7
```

Example, Alpine 3.7:

```
$ lxc image copy images:alpine/3.7 local: --alias alpine/3.7
```

# Create a new container from an image

Example, Ubuntu 18.04 container called `web`:

```
$ lxc launch ubuntu/18.04 web
```

# List current containers

```
$ lxc list
```

# Start/stop conatiners

```
$ lxc start web
$ lxc stop web
```

# Execute a command on a container

```
$ lxc exec web -- CMD
```

Useful for getting a quick terminal:

```
$ lxc exec web -- /bin/bash
```

# Snapshots

## Create Snapshot

```
$ lxc stop CONTAINER
$ lxc snapshot CONTAINER SNAPSHOT_NAME
$ lxc start CONTAINER
```

## Restore Snapshot

```
$ lxc stop CONTAINER
$ lxc restore CONTAINER SNAPSHOT_NAME
$ lxc start CONTAINER
```

## View Snapshot

```
$ lxc info CONTAINER
Name: CONTAINER
Remote: unix://
Architecture: x86_64
Created: 2018/01/16 03:02 UTC
Status: Stopped
Type: persistent
Profiles: default
Snapshots:
  SNAPSHOT_1 (taken at 2018/01/16 03:13 UTC) (stateless)
  SNAPSHOT_2 (taken at 2018/02/23 15:29 UTC) (stateless)

```

## Export Container to Image

```
$ lxc publish CONTAINER_NAME --alias my-export
```

Can also publish specific snapshot to an image:

```
$ lxc publish CONTAINER_NAME/SNAPSHOT --alias my-export
```
