***# Mounting:***

Process of making a filesystem stored on a storage device (hard disk, SSD, USB drive, CD/DVD, etc.) accessible through the Linux directory tree.



***In simple words:***

Mounting means attaching a filesystem to a directory (called a mount point) so users and applications can access its files.



***# Mount Point:***

A mount point is simply an empty directory where another filesystem is attached.





***# Without mounting:***

Disk and Filesystem exists but Linux cannot access it.





***# With Mounting:***

Partition on Storage Device driver (/dev/sdb1, /dev/sdb2, /dev/sdb3)

↓

Mount (Attaching filesystem to a Empty Directory)

↓

/Mounting\_Directory

↓

Users access files (After Mounting user can access that mounted partition 





***# What is /etc/fstab?***

It is a configuration file that tells Linux: These filesystems should be mounted automatically during system startup.





***# Basic Disk Partitioning and Mounting:***

1. lsblk 				# list the block devices



2\. sudo fdisk -l 			# list all partitions



3\. sudo fdisk /dev/sda 			# manage partitions on disk



4\. sudo mkfs.ext4 /dev/sda1 		# create filesystem (ext4)

&#x20;  sudo mkfs.xfs /dev/sda2 		# create filesystem (xfs) 



5\. sudo mkdir /mnt/dir1 			# create mount points

&#x20;  sudo mkdir /mnt/dir2 



6\. sudo mount /dev/sda1 /mnt/dir1 		# mount partitions

&#x20;  sudo mount /dev/sda2 /mnt/dir2 

\# It will Works until reboot. After restart Mount disappears.



7\. df -h 					# check disk usage



\# To make Permanent Mount Now Linux mounts automatically during boot add following entries.

8\. sudo vim /etc/fstab 			# edit fstab for permanent mount

\# partition     mount point     fs     defaults        defaults 

/dev/sda1       /mnt/dir1      ext4    defaults        0 0 

/dev/sda2       /mnt/dir2      ext4    defaults        0 0





9\. To Unmount filesystem: sudo umount /backup or sudo umount /dev/sdb1





***# Real Production Example:***

Suppose a database server runs out of storage. Admin adds a new disk.



Steps:

*Attach disk*

*↓*

*Create partition*

*↓*

*Create filesystem*

*↓*

*Create mount point*

*↓*

*Mount*

*↓*

*Update /etc/fstab*

