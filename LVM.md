***# LVM (Logical Volume Manager):***

A storage management layer in Linux that sits between physical disks and the filesystem. It abstracts physical storage into logical volumes, allowing administrators to resize, extend, or manage storage dynamically without depending on fixed disk partitions.



***# Problem:***

Traditional disk partitions are fixed in size. Suppose I create a 100 GB partition for /home, and after six months it becomes full. With normal partitioning, increasing its size can be difficult and may require repartitioning or downtime. LVM solves this problem by allowing storage to be extended dynamically.



***# Architecture:***

*Physical Disk*

*↓*

*Physical Volume (PV)*

*↓*

*Volume Group (VG)*

*↓*

*Logical Volume (LV)*

*↓*

*Filesystem (ext4/XFS)*

*↓*

*Mount Point*





1. ***Physical Volume:***

Physical Volume is the actual storage device, like a hard disk or SSD, that has been initialized for use with LVM.



***2. Volume Group:***

A Volume Group combines one or more Physical Volumes into a single storage pool. Instead of managing each disk separately, we manage the pooled storage.



***3. Logical Volume:***

Virtual partitions created from the Volume Group. These are the volumes on which we create filesystems and mount for use.



***# Real Example:***

Suppose I have two 500 GB hard disks. Instead of using them separately, I initialize both as Physical Volumes and combine them into a single 1 TB Volume Group. From that pool, I can create a 200 GB logical volume for /home, a 300 GB logical volume for /var, and leave the remaining space unallocated. If /var grows in the future, I can extend its logical volume without repartitioning the disks.



***# Benefits:***

The biggest advantages of LVM are flexibility and scalability. Logical volumes can be resized without recreating partitions, additional disks can be added to an existing Volume Group, snapshots can be created before upgrades or backups, and storage management becomes much easier in production environments.



***# LVM is widely used:***

Linux servers, virtualization platforms, cloud instances, database servers, and enterprise systems where storage requirements change over time.





***# LVM Creation and Mounting:***

lsblk 				# list block devices

sudo fdisk -l 			# list partitions



sudo fdisk /dev/sda 		# create partitions on disks

sudo fdisk /dev/sdb 



sudo pvcreate /dev/sda1 	# create physical volumes

sudo pvcreate /dev/sdb1 



sudo pvdisplay 			# display physical volumes



sudo vgcreate myvg /dev/sda1 /dev/sdb1 	# create volume group

sudo vgdisplay 				# display volume group



sudo lvcreate -n lv1 -L 1024M myvg 	# create logical volumes

sudo lvcreate -n lv2 -L 2.5G myvg 



sudo lvdisplay 				# display logical volumes



sudo mkfs -t ext4 /dev/myvg/lv1 	# create filesystem on logical volumes

sudo mkfs -t ext4 /dev/myvg/lv2 



sudo mount /dev/myvg/lv1 /mnt/dir1 	# mount logical volumes

sudo mount /dev/myvg/lv2 /mnt/dir2 



df -Th 					# check mounted filesystems with type



sudo vim /etc/fstab 			# edit fstab for permanent mount add following entries

\# partition          mount point     fs      defaults        defaults 

/dev/mapper/myvg-lv1 /mnt/dir1      ext4    defaults         0 0 

/dev/mapper/myvg-lv2 /mnt/dir2      ext4    defaults        0 0 

