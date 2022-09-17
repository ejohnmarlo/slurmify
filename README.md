# slurmify

# Prerequisites
## Make sure the clocks, users and groups (UIDs and GIDs) are synchronized across the cluster.
```
sudo timedatectl set-timezone Asia/Manila
sudo adduser -u 1001 munge --disabled-password --gecos ""
sudo adduser -u 1002 slurm --disabled-password --gecos ""
``` 

## Modify `/etc/hosts` on all nodes
Add entries
```
10.158.20.10 controller
10.158.20.11 worker
```

## Modify hostname for all node
```
sudo hostnamectl set-hostname controller
sudo hostnamectl set-hostname node01
```
