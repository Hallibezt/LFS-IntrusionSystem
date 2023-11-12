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
- $LFS variable

### Date: [11-11-2023]

**Today's Goals:**
- Finish the partition mounting
- env varibles etc
- start installing packages

**Tasks Completed:**
- Partition is correctly mounted
- Env. variable LFS=/mnt/lfs is set for user and root
- Download and make ready for installation the packet list from LFS

**Problems/Challenges Encountered:**
- No issues for now, but will have do fix some pathces when installing

**Solutions/Workarounds Implemented:**
- Nothing special for task 1 and 2
- Downloaded the packet list from LFS with wget and then ran the md5sum - all of them passed
- Changed the owner ship of all the files in $LFS/sources/* to root so that I do not get unnamed UID in the LFS: chown root:root $LFS/sources/*

**Reflections:**
- Still, straight forward to follow the LFS handbook, takes time just because I want to understand what I am doing.

**Next Steps:**
- Read the LFS handbook
- Prepare the environment

### Date: [12-11-2023]

**Today's Goals:**
- Keep on working on the LFS build

**Tasks Completed:**
- Creating the directories needed such as /etc, /var, /usr/lib, /usr/bin, /usr/sbin and the soft links for /usr/ directories
- Created the first user to avoid running only root in the new lfs: username lfs group lfs
- Some effords to make a clean working environment for the lfs user, no contimination from the host system.

**Problems/Challenges Encountered:**
-mv -v /etc/bash.bashrc /etc/bash.bashrc.NOUSE   when I am finished with lfs user, I can change this back without the ".NOUSE" part

**Solutions/Workarounds Implemented:**
- The new user lfs is so that I do not need to run the host root all the time, and possible break my host system
- The new user will get "root" ownership of the $LFS system by:
   -  chown -v lfs $LFS/{usr{,/*},lib,var,etc,bin,sbin,tools}
   -  case $(uname -m) in
   -  x86_64) chown -v lfs $LFS/lib64 ;;
   -  esac

**Reflections:**
- Pages 32-34 good about how the host system can impact .bash_profile, .bashrc and the PATH variable

**Next Steps:**
- Read the LFS handbook, Part III about the cross toolchain
- Chapter 5, compile and install the first packages


