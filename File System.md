A file system is the method used by an operating system to organize, store, retrieve, and manage files on storage devices. It maintains file names, directory structures, metadata, permissions, and free space information. Windows commonly uses FAT16, FAT32, and NTFS, while Linux commonly uses Ext4 and XFS. FAT16 and FAT32 are simple and highly compatible but lack features such as journaling, permissions, and support for very large files. NTFS is the default Windows file system and provides journaling, access control lists, encryption, compression, and support for large files and volumes. In Linux, Ext4 is the most widely used general-purpose file system due to its stability, journaling, extents, and good performance. XFS is designed for enterprise environments, offering excellent performance for large files, high throughput, parallel I/O, and online filesystem expansion. The choice of file system depends on the operating system, workload, compatibility requirements, and performance needs.

***(For Quick Revision Refer Last Summary Table)***



***# File System:***

a method used by an operating system to organize, store, retrieve, and manage files and directories on a storage device such as an HDD, SSD, USB drive, or memory card. It defines how data is named, stored, accessed, protected, and deleted.



***# General File System Architecture:***

User

↓

Application

↓

Operating System

↓

File System (NTFS, FAT, XFS, EXT4)

↓

Storage Device (SSD, HDD, USB Drives)

↓

Blocks / Sectors





***# FAT (File Allocation Table):***

* Microsoft's oldest file system Developed in 1977
* It is simple and lightweight.
* It stores file locations using a File Allocation Table.
* No permissions, No encryption, No compression, No journaling
* The FAT keeps track of the chain.



1. **FAT16**

Old version of FAT.

Maximum partition ≈2 GB

Maximum file ≈2 GB

Used in DOS/old Windows, Old Windows, Embedded devices



**2. FAT32**

Most famous FAT version.

Maximum file size 4 GB

Maximum partition Up to 2 TB (Windows formatting tools commonly limit creation to 32 GB, though the format itself supports much larger volumes.)

Used in USB Drives, Memory Cards, Cameras, BIOS/UEFI updates.

Lacks Advanced Security Feature.



***# FAT16 and FAT32 had many limitations:***

No file security

No user permissions

No encryption

Maximum file size of 4 GB (FAT32)

Poor recovery after power failure





**# NTFS (New Technology File System) :**

* The default file system ***used in Windows*** operating systems.
* It was introduced to ***overcome the limitations of FAT32 by providing advanced features*** such as journaling, file permissions, encryption, compression, disk quotas, and support for very large files.
* NTFS ***stores information about every file in a Master File Table (MFT),*** which contains metadata such as file name, size, permissions, and disk location. This makes NTFS secure, reliable, and suitable for both personal computers and enterprise servers.
* NTFS used in: Windows 10/11, Windows Server, Office PCs, Gaming PCs, Laptops, Enterprise servers
* Key Features: 



**NTFS working:**

Imagine you save a file called Resume.pdf.

NTFS creates an entry in a special database called the Master File Table (MFT).

The MFT stores information such as: File name, File size, Owner, Permissions, disk Location, Creation and modification time



Resume.pdf

↓

Master File Table (MFT)

↓

File Size : 2 MB

Owner : Shambhu

Permissions : Read, Write

Location : Block 120, 121, 122



When you open the file, Windows first checks the MFT to find where the file is stored.





***# EXT4 (Fourth Extended File System):***

* The most widely used Linux file system, providing journaling, inodes, high performance, and reliability for ***general-purpose Linux systems.***
* EXT4 ***stores file metadata using inodes***, which contain information such as file ownership, permissions, timestamps, and block locations. 
* Because of its stability and performance, EXT4 is widely ***used for desktops, servers, and virtual machines running Linux***
* It is the default file system in many Linux distributions such as: Ubuntu, Debian, Fedora, Linux Mint.





***# XFS:***

* XFS is a high-performance journaling file system ***designed for enterprise Linux environments***. 
* It is ***optimized for large files, high-capacity storage systems, and parallel read/write operations***. 
* Like EXT4, it ***uses inodes to store file metadata***, but it is designed to deliver better performance for workloads such as databases, video streaming, and large storage servers. 
* XFS ***supports online filesystem expansion*** and fast recovery after crashes, making it a popular choice for enterprise deployments.
* Today it is commonly used in: RHEL, CentOS, Rocky Linux, Enterprise Linux servers.



| ------------------- | ----------------------- | ----------------------------- | ------------------------------------------------ |

| Feature             | NTFS                    | EXT4                          | XFS                                              |

| ------------------- | ----------------------- | ----------------------------- | ------------------------------------------------ |

| Operating System    | Windows                 | Linux                         | Linux                                            |

| Default File System | Windows                 | Many Linux distributions      | Common in many RHEL-based enterprise deployments |

| Journaling          |  Yes                    |  Yes                          |  Yes                                             |

| Metadata Structure  | Master File Table (MFT) | Inodes                        | Inodes                                           |

| Security            | ACL, EFS                | Linux permissions + ACL       | Linux permissions + ACL                          |

| Best For            | Windows PCs \& Servers   | General-purpose Linux systems | Enterprise servers \& large storage               |

| Performance         | Excellent               | Excellent                     | Excellent for large files and heavy I/O          |

| Large Files         |  supported              | Supported                     | Best Support                                     |

| Online Expansion    | Limited                 | Yes (with supported tools)    | Yes                                              |

| ------------------- | ----------------------- | ----------------------------- | ------------------------------------------------ |



