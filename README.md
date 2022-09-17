# slurmify

# Prerequisites
Root user.
Tested on Ubuntu 20.04

## Make sure the clocks, users and groups (UIDs and GIDs) are synchronized across the cluster.
```sh
sudo timedatectl set-timezone Asia/Manila
sudo adduser -u 1001 munge --disabled-password --gecos ""
sudo adduser -u 1002 slurm --disabled-password --gecos ""
``` 

## Modify `/etc/hosts` on all nodes
Add entries
```
10.158.20.10 samsung-slurm-controller
10.158.20.11 samsung-slurm-node01
```

## Modify hostname for all node
```sh
sudo hostnamectl set-hostname samsung-slurm-controller
sudo hostnamectl set-hostname samsung-s1
```

## Modify `.ssh/config` for controller node
```
Host controller
  Hostname 10.158.20.10
  User root
  Port 22

Host samsung-s1
  Hostname 10.158.20.11
  User root
  Port 22
```
