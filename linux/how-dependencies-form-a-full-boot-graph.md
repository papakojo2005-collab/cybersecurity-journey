**How Dependencies form a full boot graph**



Contrary to what I used to believe, the Linux boot process in new Linux-based systems is not a sequential series of steps because of systemd, which uses aggressive
parallelization techniques to start several processes, respecting dependencies.



**Types of Dependencies**



1. Requires=
Also called a hard dependency. If it fails the unit will also fail.
2. Wants=
Also called a soft dependency. The unit does not depend strictly on it.
3. After/Before=
Not typically a dependency. Indicates what services should be started before or after the main unit.

The GUI for example, is a target called graphical.target, and is the default target in most Linux systems.

Depends on:

* multi-user.target

which depends on:

* networking
* login services
* system logging

networking depends on:

* network interfaces
* login services
* udev



**Key Insight**



The Linux system is now adapted for speed, which transfers to workflows in the digital world, unlike old init systems that had to run steps one by one.

