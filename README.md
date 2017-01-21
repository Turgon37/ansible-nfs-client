Ansible Role NFS Client
========

This roles allow configuration of NFS client features

## OS Family

This role is available for RedHat

## Features

At this day the role can be used to configure :

  * Fstab with nfs mount entries
  * NFS packages
  * NFS RPC daemon


## Configuration

The following parameters are available in the role. Some of them are well documented into gammu and gammu-smsd man pages :

| Name                  | Required ? | Description                 |
| ----------------------|----------- |---------------------------- |
| nfs_client__mounts    | mandatory  | The list of networks shares |

### Example of configuration

  * Two NFS networks shares from a NAS

```
nfs_client__mounts:
  - name: /mnt/storage/
    src: 10.0.0.5:/volume1/storage
    fstype: nfs
    options: defaults,intr,auto,vers=3
  - name: /mnt/homes/
    src: 10.0.0.5:/volume1/homes
    fstype: nfs4
    options: defaults,intr,auto,acl
```