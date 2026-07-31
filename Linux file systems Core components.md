* The core components of a Linux file system include the Boot Block, Superblock, Inode Table, Directory Structure, Data Blocks, and, in journaling file systems such as ext4 and XFS, a Journal. 



* The Superblock stores metadata about the entire file system, such as its size, block size, and free space. 



* Each file has an inode that stores metadata like permissions, ownership, timestamps, and pointers to the file's data blocks, while the filename itself is stored in the directory entry. 



* The actual file contents are stored in data blocks. The Journal records metadata changes before they are committed to disk, allowing the file system to recover quickly and maintain consistency after an unexpected shutdown or power failure. Together, these components allow Linux to efficiently organize, locate, and manage files.



***# Journaling:***

* It is a technique where a file system first records pending changes in a journal before applying them to the disk. This helps recover safely from crashes or power failures and prevents file system corruption.
* Before making any changes to the file system, it first records the intended operation in a special area called the journal.



*Record Operation in Journal*

&#x20;         *↓*

*Write Changes to Disk*

&#x20;         *↓*

*Mark Journal Entry Complete*





| ----------- | ------------------------------------------------------------- |

| Component   | Purpose                                                       |

| ----------- | ------------------------------------------------------------- |

| Boot Block  | Contains boot-related information used during system startup. |

| Superblock  | Stores metadata about the entire file system.                 |

| Inode Table | Stores metadata for each file (except the filename).          |

| Directory   | Maps filenames to inode numbers.                              |

| Data Blocks | Store the actual contents of files.                           |

| Journal     | Records pending file system changes for crash recovery.       |

| ----------- | ------------------------------------------------------------- |





***# How Linux Opens a File:***

Suppose you type: cat report.txt

Linux performs these steps:



*User*

*↓*

*Directory*

*↓*

*Find report.txt*

*↓*

*Inode Number*

*↓*

*Read Inode*

*↓*

*Locate Data Blocks*

*↓*

*Read File*

*↓*

*Display Content*

