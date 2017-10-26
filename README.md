# Rancher SSH

SSH into your Rancher Host using Rancher CLI

## Install

```
$ sudo curl -o /usr/local/bin/rssh -L "https://github.com/joshuamarquez/rancher-ssh/releases/download/1.0.0/rssh"
$ sudo chmod +x /usr/local/bin/rssh
```

## Usage

```
$ rssh user@hostname
```

* `user` - Host username.
* `hostname` - Rancher hostname as specified in column `HOSTNAME` from `$ rancher host` output.

## Requirements

* Rancher CLI installed
* Authenticated in some Rancher Environment

## How it works

1. Look for a host that matches `hostname` and with state `active`.
2. Find a running cointainer with ssh installed.
3. Using container found in step 2, we get docker host ip.
4. We ssh into host executing command `ssh username@dockerhostip` in container with ssh installed.
