Hypervisor Development for the Intel and UEFI Platform
=======================================================

Overview
---------

This course provides students the skills and knowledge to develop their pass-though hypervisors as UEFI modules using Intel VT-x. This is a hands-on heavy class and will spend more than 60% of the time with excesses.

Audiences
----------

This class is geared towards software developers and others with an interest in expanding knowledge of Intel VT-x, the x86_64 system architecture, and/or UEFI.


Levels
-------

- Intermediate to advanced


Prerequisites
--------------

Required:
- Strong experience in C (or C++) programming.
- Familiarity with the x86_64 architecture, such as privilege levels, interrupts, page tables, and system registers.
- System programming experience, such as kernel-module development.


Learning Objectives
--------------------

At the end of the class, students will gain sufficient knowledge and skills to start developing their pass-through UEFI-based hypervisors. Knowledge-wise, this includes but not limited to the understanding of:
- Key concepts of VT-x and programming interfaces
- Execution environment changes during OS boot and their influence on the hypervisor design
- Subtle yet critical technologies such as memory types and caches
- Application Processors (APs) start up, and emulation by a hypervisor
- "Owning" control registers
- UEFI-module development workflow and tools
- The pros and cons of UEFI-based vs OS kernel module-based hypervisors


Outlines
---------

1. UEFI and Hypervisors
    - Background: why UEFI for hypervisors, differences from OS kernel drivers, EDK2
    - Lab: setting up the lab environment
    - Lab: debugging firmware modules and logging output
2. Basics of VT-x
    - Background: processor modes, VMCS, "host" vs "guest", VM-exit and VM-entry
    - Lab: configuring host and guest
    - Lab: starting host and guest, monitoring system activities
3. OS Boot
    - Background: system boot stages, boot time vs runtime, physical vs virtual mode
    - Lab: using a runtime driver for monitoring OS activities
    - Lab: handling boot to runtime, and physical to virtual transitions
5. Extended Page Tables (EPT)
    - Background: address translation, memory types, EPT programming interface, and VM-exit
    - Lab: translating virtual address to physical address by hands
    - Lab: interpreting memory type configuration
    - Lab: enabling EPT and observing VM-exits
    - Lab: debugging EPT issues
6. Multi-processors Support
    - Background: protocols, processor activity-state, application processors startup, and unrestricted guest
    - Lab: virtualizing all processors
    - Lab: emulating INIT-SIPI-SIPI
    - Lab: starting application processors
7. Features and Fun
    - Lab: each student will select one of the self-paced exercises and work on it

Contents may change in a way that does not impact the learning objectives.


Details
--------

Hypervisors are becoming more important in the area of cloud computing and security. There is an increasing interest in using hypervisors in the area of security engineering and analysis. How can hypervisors help protect against tampering of the guest OS or other software? How can it be used in malware analysis? What about cheats and anti-cheats in the games industry?

This course provides students the skills and knowledge to develop their hypervisors using Intel VT-x. It is designed in a way such that everything is built from scratch. This emphasis allows students to better understand the building blocks and nuances behind a hypervisor, as well as expanding knowledge acquired in the course by themselves. Topics include UEFI firmware programming, VT-x initialization, debugging, nested page tables, and more. Students will develop a hypervisor that implements a variety of exit handlers and offering useful demo features at the end.

This is a hand-on oriented class. We believe that the students can learn and retain concepts and skills the best by working with those by themselves and not by being taught; hence offering the maximum value to the students. With this philosophy, the class is designed for lab activities as the primary learning opportunities, and lectures are to explain backgrounds for the lab activities. We will spend more than 60% of the time with hands on.

![Hypervisor_Development_on_Intel_and_UEFI_Platform.png](/Images/Hypervisor_Development_on_Intel_and_UEFI_Platform.png)

Pricing
--------

| Type       | Individual | Company  |
|------------|------------|----------|
| Early Bird | 1800 USD   | 3600 USD |
| Standard   | 2000 USD   | 4000 USD |

All prices are per seat.

- Individual vs Company: We price the class differently depending on whether it is paid by an individual.
- Early Bird: We offer 10% discount if registration is done by 45 days before the first day of the class.
- Repeater: We may offer a discount if the student took one of our classes previously. During registration, tell us when the student took the class.


Format and Package
-------------------

Format:
- Remote - The training is offered remotely through Zoom.
- Synchronous - The training is offered live.

Package:
- Material - Training materials (slides, sample code etc).
- Support - 3 weeks of asynchronous consultation on Slack and email from the last day of the class.


Hardware and Software Requirements
-----------------------------------

The students are expected to have the following hardware and software:

- The host machine with the Intel processor, SSD, and 8GB+ RAM
- For Windows users
    - Windows 10 x64 build 19042 (a.k.a. 20H2) without Virtualization-base Security (VBS) enabled
    - Ubuntu 20.04 on WSL version 1
    - VMware Workstation Pro or VMware Workstation Player 16
- For Linux users
    - Ubuntu 20.04
    - VMware Workstation Pro or VMware Workstation Player 16
- As VMs, Windows 10 x64 build 19042 and Ubuntu 20.04

The other configuration, such as another Linux distro may be workable but unsupported. The macOS host or other hypervisors such as KVM, Hyper-V, or VirtualBox cannot be used.

The host system can also be a cloud-provided machine. If the host machine cannot be arranged locally, we recommend the student to look into:
- Scaleway's bare metal server [GP-BM1-S](https://www.scaleway.com/en/pricing) for a Linux host, and
- Amazon's bare metal server [m5zn.metal](https://aws.amazon.com/ec2/pricing/on-demand/) for a Windows host

The students are expected to complete the setup instructions that will be sent by the instructor before the class.


Registration and Contacts
--------------------------

For registration and further inquires, please reach out to us
- [via email](mailto:tanda.sat@gmail.com?cc=bruce.dang@gmail.com&subject=%20Hypervisor%20Development%20for%20the%20Intel%20and%20UEFI%20Platform), or
- DM to [@standa_t](https://twitter.com/standa_t) on Twitter
