#### findmnt – Shows Currently Mounted File Systems in Linux. To list all mount points in system ( tree format ) :

```

[tuttu@fedora ~]$ findmnt
TARGET                         SOURCE      FSTYPE   OPTIONS
/                              /dev/sda2[/root]
                                           btrfs    rw,relatime,seclabel,compress=zstd:1,space_c
├─/proc                        proc        proc     rw,nosuid,nodev,noexec,relatime
│ └─/proc/sys/fs/binfmt_misc   systemd-1   autofs   rw,relatime,fd=31,pgrp=1,timeout=0,minproto=
│   └─/proc/sys/fs/binfmt_misc binfmt_misc binfmt_m rw,nosuid,nodev,noexec,relatime
├─/sys                         sysfs       sysfs    rw,nosuid,nodev,noexec,relatime,seclabel
│ ├─/sys/kernel/security       securityfs  security rw,nosuid,nodev,noexec,relatime
│ ├─/sys/fs/cgroup             cgroup2     cgroup2  rw,nosuid,nodev,noexec,relatime,seclabel,nsd
│ ├─/sys/fs/pstore             pstore      pstore   rw,nosuid,nodev,noexec,relatime,seclabel
│ ├─/sys/fs/bpf                bpf         bpf      rw,nosuid,nodev,noexec,relatime,mode=700
│ ├─/sys/fs/selinux            selinuxfs   selinuxf rw,nosuid,noexec,relatime

```

#### To display in ordinary list format :

```
tuttu@fedora ~]$ findmnt -l
TARGET                   SOURCE      FSTYPE   OPTIONS
/proc                    proc        proc     rw,nosuid,nodev,noexec,relatime
/sys                     sysfs       sysfs    rw,nosuid,nodev,noexec,relatime,seclabel
/dev                     devtmpfs    devtmpfs rw,nosuid,seclabel,size=4096k,nr_inodes=1048576,mo
/sys/kernel/security     securityfs  security rw,nosuid,nodev,noexec,relatime
/dev/shm                 tmpfs       tmpfs    rw,nosuid,nodev,seclabel,inode64
/dev/pts                 devpts      devpts   rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,
/run                     tmpfs       tmpfs    rw,nosuid,nodev,seclabel,size=779496k,nr_inodes=81
/sys/fs/cgroup           cgroup2     cgroup2  rw,nosuid,nodev,noexec,relatime,seclabel,nsdelegat
/sys/fs/pstore           pstore      pstore   rw,nosuid,nodev,noexec,relatime,seclabel
```

#### To list only real file sytems :

```
$ findmnt --real
TARGET  SOURCE           FSTYPE   OPTIONS
/       /dev/sda2[/root] btrfs    rw,relatime,seclabel,compress=zstd:1,space_cache=v2,subvolid=2
├─/run/user/1000/doc
│       portal           fuse.por rw,nosuid,nodev,relatime,user_id=1000,group_id=1000
├─/boot /dev/sda1        ext4     rw,relatime,seclabel
└─/home /dev/sda2[/home] btrfs    rw,relatime,seclabel,compress=zstd:1,space_cache=v2,subvolid=2
```

