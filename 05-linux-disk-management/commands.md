e%
Mounted on
Option
-h → Human-readable format
2. du -sh
Command
du -sh ~
Purpose

Shows the total disk space used by a directory.

Options
-s → Summary
-h → Human-readable format
3. du -sh ~/*
Command
du -sh ~/*
Purpose

Shows the size of each file and directory inside the home directory.

This is useful for finding which directories are consuming the most disk space.

4. lsblk
Command
lsblk
Purpose

Shows information about:

Disks
Partitions
Partition sizes
Mount points
5. lsblk -f
Command
lsblk -f
Purpose

Shows disk, partition, and filesystem information.

Important Columns
NAME
FSTYPE
FSVER
LABEL
UUID
MOUNTPOINTS

Example filesystem:

ext4
6. mount
Command
mount
Purpose

Shows the filesystems currently mounted on the Linux system.

Mounting makes a filesystem accessible through a directory.

7. umount
Command
sudo umount /mount/point
Purpose

Unmounts a filesystem from its mount point.

Example:

sudo umount /data

Be careful when using umount on system filesystems.

Filesystem

A filesystem is the system Linux uses to organize, store, and manage files and directories on a storage device.

Common Linux filesystem:

ext4
Filesystem Structure
Disk
 ↓
Partition
 ↓
Filesystem
 ↓
Mount Point
 ↓
Directory
 ↓
Files
Disk vs Partition vs Filesystem
Disk       → Physical or virtual storage device
Partition  → Section of a disk
Filesystem → System that organizes data on a partition
Mount      → Makes the filesystem accessible through a directory
Directory  → Folder used to organize files
Important Difference
df -h       → Shows filesystem/disk space
du -sh      → Shows directory/file disk usage
lsblk       → Shows disks and partitions
lsblk -f    → Shows filesystem details
mount       → Shows mounted filesystems
umount      → Unmounts a filesystem
Real-World Disk Investigation

If a server reports:

Disk Usage = 95%

First check the filesystem:

df -h

Then investigate directory usage:

du -sh ~/*

The general process is:

df -h
   ↓
Find filesystem with high usage
   ↓
du -sh
   ↓
Find large directory
   ↓
Investigate further
   ↓
Find what is consuming disk space
Quick Revision
Command Purpose
df -h   Shows filesystem disk space
du -sh  Shows directory/file disk usage
du -sh ~/*  Shows sizes of items in home directory
lsblk   Shows disks and partitions
lsblk -f    Shows filesystem details
mount   Shows mounted filesystems
umount  Unmounts a filesystem
Key Points
Disk provides storage.
Partition divides a disk.
Filesystem organizes data.
Mount point provides access to a filesystem.
df checks filesystem space.
du checks directory/file usage.
lsblk shows disk and partition structure.
lsblk -f shows filesystem information.
mount shows mounted filesystems.
umount removes a filesystem from its mount point.
