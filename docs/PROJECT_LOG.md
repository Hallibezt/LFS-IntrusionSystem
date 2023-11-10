# Project Log

This document serves as a chronological log of the work done on the Custom Linux Network Monitoring and Intrusion Detection System. It includes the dates of significant milestones, problems encountered, solutions implemented, and any other relevant notes and reflections.

---

## Log Entry Template

### Date: [05-11-2023]

**Today's Goals:**
- Preparation, Creating GitHub Repo, 
- Setting up the documents and Downloading the LFS handbook and start reading
- Install Ubuntu server 22.04 on the laptop (Acer Aspire ONE 725 -C62kk  2012/06/21)
 

**Tasks Completed:**
- Set up Github, created doc files
- Installed Ubuntu server as the host system on the laptop
- Tested the version-check.sh script on the local machine (with the packages requirements for the LFS build)

**Problems/Challenges Encountered:**
- Problem 1 - Overwhelming complixity
- ...

**Solutions/Workarounds Implemented:**
- Solution to Problem 1 - Prepare the ground, starting with setting up the version control environment and document everything, AKA using this log
- Download the LFS, and start focusing on that BEFORE even thinking so much about the C/C++ programming part.

**Reflections:**
- Stay focused, small steps at the time. Take time to document and plan.

**Next Steps:**
- Read the LFS handbook
- Configure git and openssh on the laptop
- SCP the version-check.sh to the laptop, check and install missing packages/or update
- Partion the disk and start the LFS build


### Date: [06-11-2023]

**Today's Goals:**
- Configure ssh on the laptop - 192.168.0.40 static IP
- SCP version.check to laptop and get what is required
- Configure the GitHub account on the laptop


**Tasks Completed:**
- Configure ssh on the laptop - 192.168.0.40 static IP
- SCP version.check to laptop and get what is required

**Problems/Challenges Encountered:**
- None, just need to understand all these compiler things better: bison, m4, make etc

**Solutions/Workarounds Implemented:**
- All good, nothing special

**Reflections:**
- Went well, don't have time for git now. Have to go to sleep.

**Next Steps:**
- Set up git on the lap
- Read the LFS handbook
- Partion the disk and start the LFS build

### Date: [07-11-2023]

**Today's Goals:**
- Set up git on the lap

**Tasks Completed:**
- Task finished 

**Problems/Challenges Encountered:**
- The ssh client trying to use PAM but fail

**Solutions/Workarounds Implemented:**
- sudo vim /etc/ssh/ssh_config had to comment out Usepam = no

**Reflections:**
- Not much to day, much that had to be done to day personally.

**Next Steps:**
- Read the LFS handbook
- Partion the disk and start the LFS build
- Start practicing c++ with the C++ book

### Date: [10-11-2023]

**Today's Goals:**
- Create a partition for LFS

**Tasks Completed:**
- Task finished

**Problems/Challenges Encountered:**
- Understanding the filesystem and the different partitions needed is a complex thing. A LVM (Logical Volume Manager) makes this task a little easier since
- I use Ubuntu 22 server as my host system I have this option. This means that I can focus now on the main LFS partitions and then create the extra partitions later if 
- needed, e.g for /tmp or /data etc

**Solutions/Workarounds Implemented:**
- I created a 50 Gb logical volume named lfs from the ubuntu-vg LVM: "sudo lvcreate -L 50G -n lfs ubuntu-vg" then I formatted it as ext4 and mounted it on /mnt/lfs:
- sudo mkfs.ext4 /dev/ubuntu-vg/lfs 
mke2fs 1.46.5 (30-Dec-2021)
Creating filesystem with 13107200 4k blocks and 3276800 inodes
Filesystem UUID: 43777f27-5c41-4022-a904-fc4b04e64d9c
Superblock backups stored on blocks: 
	32768, 98304, 163840, 229376, 294912, 819200, 884736, 1605632, 2654208, 
	4096000, 7962624, 11239424

Allocating group tables: done                            
Writing inode tables: done                            
Creating journal (65536 blocks): done
Writing superblocks and filesystem accounting information: done  

- sudo mkdir /mnt/lfs
- sudo mount /dev/ubuntu-vg/lfs /mnt/lfs
- The Ubuntu system is using a large enoug swap file for the LFS to use also: (+NAME):swapon --show    +NAME /swap.img file 3.6G   0B   -2

**Reflections:**
- Not much to day, much that had to be done to day personally.

**Next Steps:**
- Read the LFS handbook
- Partion the disk and start the LFS build
- Start practicing c++ with the C++ book

