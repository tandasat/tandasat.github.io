Hypervisor Development for Security Researchers
================================================

Overview
---------

This course helps students gain the skills and knowledge to develop light-weight hypervisors as UEFI modules using Intel VT-x. This is a hands-on heavy class and will spend about 40% of the time with excesses.


Audiences
----------

This class is geared towards software developers, security researchers and others with an interest in expanding knowledge of Intel VT-x, the x86_64 system architecture, and/or UEFI.


Levels
-------

- Intermediate to advanced


Prerequisites
--------------

Required:
- Strong experience in C (or C++) programming.
- Familiarity with the x86_64 architecture, such as privilege levels, interrupts, page tables, and system registers.
- System programming experience, such as kernel-module development, is a plus but not a requirement.

Recommended pre-class learning materials will be introduced about 3 weeks prior to the class.


Learning Objectives
--------------------

At the end of the class, students will gain enough knowledge and skills to start developing their pass-through hypervisors. Knowledge-wise, this includes but not limited to the understanding of:

- Key concepts of VT-x and programming interfaces
- Various applications of hypervisors in the real world and how they are implemented, examples include:
  - System hardening, such as HVCI and KDP on Windows
  - System-level fuzzing, such as What The Fuzz
  - System-level inspection and rootkit, such as antivirus-hypervisors
- Early OS boot activities and handling of them as a hypervisor
- Subtle yet complex concepts such as control register access, memory types, caches invalidation, and emulation of those
- Basic UEFI-module development workflow, tools and techniques


Outlines
---------

1. Hypervisor and UEFI
    - Lectures: what hypervisors can be used for, UEFI module-based hypervisors, comparison with kernel module-based hypervisors, and UEFI/EDK2

2. VT-x Basics
    - Lectures: processor modes, VMCS, "host" vs "guest", VM-exit, VM-entry, and high-level design options
    - Lab: source-level debugging with VMware
    - Lab: configuring and starting host and guest, monitoring CPUID execution
    - Lab: troubleshooting VMX instruction errors with Bochs

3. OS Boot
    - Lectures: system boot phases, boot time vs runtime, physical vs virtual mode, and runtime drivers for monitoring OS activities
    - Lab: controlling VM-exits with MSR bitmaps
    - Lab: booting Windows by building host page tables
    - Lab: tracing guest page faults with exception interception and event injection

4. Extended Page Tables (EPT)
    - Lectures: traditional x64 address translation vs EPT-enabled translation, EPT setup and activation, EPT induced VM-exits
    - Lab: building and enabling pass-through EPT
    - Lab: tracing guest execution with EPT
    - Advanced lectures: memory types emulation, caches invalidation, VPID, stealth hooking with EPT, MBEC, VT-rp (HLAT), VT-d (DMA remapping), and snapshot-based fuzzing hypervisors

5. Multi-processors Support
    - Lectures: multi-processor protocol, processor activity state, application processors startup, unrestricted guest and Hypervisor Top Level Functional Specification (TLFS)
    - Lab: virtualizing all processors
    - Lab: booting multi-processor Windows by emulating INIT-SIPI-SIPI

6. Control Register Shadowing
    - Lectures: control register guest/host mask, read shadow VMCS, and complexities with emulation of control register access
    - Lab: booting Ubuntu by properly emulating MOV-to-CRx

7. Demos and References
    - Hardware debuggers (DCI), single board computers, and relevant open source projects

Contents may change in a way that does not impact the learning objectives.


Details
--------

A hypervisor is a critical component in both security and cloud computing. There is also an increasing interest in applying virtualization technologies in the area of security engineering and analysis. How can hypervisors be used to secure the existing systems? How to write custom hypervisors to perform reverse engineering and fuzzing more efficiently?

In this class, the students will have the answers to those questions through developing simple hypervisors together. The class is designed in a way such that everything is built from scratch and optimized for learning. This allows students to better understand the building blocks of real-world applied use of virtualization technologies and expand the knowledge for their interests afterward. Topics include UEFI architecture and programming, VT-x/EPT configuration, comparison of hypervisor designs, application of the technologies, debugging tools and techniques, and more.

This is a hands-on-oriented class. We believe that the students can learn and retain knowledge best by tackling concrete challenges and not by being taught. With this philosophy, the class is designed for lab activities as the primary learning opportunities, and lectures are to explain theories behind them. We will spend about 40% of the time on hands-on exercises.

At the beginning of the class, each student will receive a skeleton implementation of hypervisor and incrementally update it through a series of exercises with an understanding of design choices.

As we learn concepts, we will discuss various applications of virtualization technologies and their implementations throughout the class. This includes snapshot-based system-level fuzzing, performant system hardening with MBEC and HLAT (VT-rp), eg, HyperGuard, HVCI and KDP on Windows, dynamic analysis with stealth-hooking, and SMM security reporting (PPAM).

Near the end of the class, students will also receive a full version of our hypervisor. This includes implementation of advanced concepts, such as stealth-hooking hypercall, use of VT-d (DMA protection), guest hardening, host hardening with CET, SMAP and UMIP, handling of uncommon events like microcode update, NMI and MTRR updates. This version can be used to complement your understanding of advanced topics and as a reference to explore more topics as you wish.

![Hypervisor_Development_for_Security_Researchers.png](/Images/Hypervisor_Development_for_Security_Researchers.png)


Pricing
--------

| Type       | Individual | Company  |
|------------|------------|----------|
| Early Bird | 2700 USD   | 3600 USD |
| Standard   | 3000 USD   | 4000 USD |

All prices are per seat.

- Early Bird: We offer 10% discount if registration is done by 60 days before the first day of the class.
- Individual vs Company: We price the class differently depending on whether it is paid by your employer or yourself.
- Students: We may offer 50% discount for a full-time students. Contact us before registration and payment.


Format and Package
-------------------

Format:
- The training is offered remotely through Zoom.
- Recording will be uploaded shortly after end of each day for review.

Package:
- Material - Training materials (slides, sample code etc) will be shared.
- Support - 3 weeks of asynchronous consultation on Slack and email from the last day of the class. Rights to request the latest slides and code for free.


Hardware and Software Requirements
-----------------------------------

The students are expected to have the following hardware and software:

- The host machines with the Intel processors, SSD, 8GB+ RAM and 50GB+ of free storage space
- For Windows users
    - Windows 10 build 22621 (a.k.a. 22H2)+ without Virtualization-base Security (VBS) enabled
    - Ubuntu 22.04+ on WSL version 1
    - VMware Workstation Pro (Recommended) or VMware Workstation Player 17
- For Linux users
    - Ubuntu 22.04+
    - VMware Workstation Pro 17
- For macOS Users
    - macOS 11+
    - VMWare Fusion Pro 12 or VMWare Fusion Player 12
    - Homebrew and git

The newer versions of the operating systems and other software are supported. Older versions of software and another Linux distro may be workable but not adequately tested. Other hypervisors such as KVM, Hyper-V, or VirtualBox cannot be used.

The host system can also be a cloud-provided machine if the host machine cannot be arranged locally. Those are confirmed to be usable:
- Scaleway's Intel [Elastic Metal Servers](https://www.scaleway.com/en/pricing/#elastic-metal) for a Linux host, and
- Amazon's Intel bare metal server [m5zn.metal](https://aws.amazon.com/ec2/pricing/on-demand/) for a Windows host

The students are expected to complete the setup instructions that will be sent by the instructor before the class.


Registration and Contacts
--------------------------

- For the dates and timezone of the next public class, see [the top page](README.md).
- For receiving updates on future public classes, subscribe [our mailing list](https://groups.io/g/system-programming-lab) by sending empty email to [system-programming-lab+subscribe@groups.io](mailto:system-programming-lab+subscribe@groups.io?subject=Subscribe%20Request).
- For further inquiries, reach out to [@standa_t](https://twitter.com/standa_t) on Twitter or [send us email](mailto:tanda.sat@gmail.com?subject=Hypervisor%20Development%20for%20Security%20Researchers). We also offer a private class with minimum 8 people. Please contact us to discuss further details.
