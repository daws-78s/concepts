# Resize EBS Storage

check the partitions
```
lsblk
```

Use a tool like growpart to resize the existing partition to fill the available space.This will resize the fourth partition (nvme0n1p4) to use the remaining unallocated space on the disk.
```
sudo growpart /dev/nvme0n1 4
```

Extend the Logical Volumes
Decide how much space to allocate to each logical volume. For example, to extend both the root and /var logical volumes:

```
sudo lvextend -l +50%FREE /dev/RootVG/rootVol
sudo lvextend -l +50%FREE /dev/RootVG/varVol
```

After extending the logical volumes, resize the filesystems to utilize the additional space.

For the root filesystem:

```
sudo xfs_growfs /
```

For the /var filesystem:

```
sudo xfs_growfs /var
```