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
