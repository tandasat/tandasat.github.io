Hypervisor Development for Security Researchers
================================================

Overview
---------

This course provides students the skills and knowledge to develop their thin hypervisors as UEFI modules using Intel VT-x. This is a hands-on heavy class and will spend about 40% of the time with excesses.


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

At the end of the class, students will gain enough knowledge and skills to start developing their pass-through UEFI-based hypervisors. Knowledge-wise, this includes but not limited to the understanding of:

- Key concepts of VT-x and programming interfaces
- General UEFI-module development workflow and tools
- Execution environment changes during OS boot and their influence on the hypervisor design
- Subtle yet critical technologies such as memory types and caches
- Application Processors (APs) start up, and emulation by a hypervisor
- "Owning" control registers and challenges with it
- Various application of hypervisors (for adding security, reverse engineering and fuzzing, for example)


Outlines
---------

1. UEFI and Hypervisors
    - Lectures: why UEFI for hypervisors, differences from OS kernel drivers, EDK2, introduction to high-level design options
    - Lab: setting up the lab environment
    - Lab: debugging firmware modules and logging output

2. Basics of VT-x
    - Lectures: processor modes, VMCS, "host" vs "guest", VM-exit, VM-entry, and snapshot and "guest" for fuzzing hypervisor
    - Lab: setting up Bochs and debugging VMX instruction issues
    - Lab: configuring host and guest
    - Lab: starting host and guest, monitoring CPUID execution

3. OS Boot
    - Lectures: system boot phases, boot time vs runtime, physical vs virtual mode, and runtime drivers for monitoring OS activities
    - Lab: controlling VM-exits with MSR bitmaps
    - Lab: booting Windows by building host page tables, IDT and GDT
    - Lab: tracing guest page faults with exception interception and event injection

4. Extended Page Tables (EPT)
    - Lectures: x64 address translation, EPT setup and activation, EPT induced VM-exits, memory types, caches, VPID, EPT-based hooking, VT-d (DMA remapping), and snapshot-based fuzzing hypervisor design
    - Lab: reviewing address translation mechanisms with and without EPT
    - Lab: enabling EPT and tracing guest execution

5. Multi-processors Support
    - Lectures: multi-processor protocol, processor activity state, application processors startup, unrestricted guest and Hypervisor Top Level Functional Specification (TLFS)
    - Lab: virtualizing all processors
    - Lab: booting multi-processor Windows by emulating INIT-SIPI-SIPI

6. Control Register Shadowing
    - Lectures: control register guest/host mask, read shadow, effects, and emulation of control register changes
    - Lab: "owning" control registers
    - Lab: booting Ubuntu by properly emulating MOV-to-CRx

7. Demos and References
    - Hardware debuggers (DCI), single board computers, and relevant open source projects

Contents may change in a way that does not impact the learning objectives.


Details
--------

A hypervisor is a critical component in both security and cloud computing. There is also an increasing interest in applying virtualization technologies in the area of security engineering and analysis. How can hypervisors be used to secure the existing systems? How to write custom hypervisors to perform reverse engineering and fuzzing more efficiently?

In this class, the students will learn the foundations to answer those questions, that is, the basic skills and knowledge to develop hypervisors. The class is designed in a way such that everything is built from scratch and optimized for learning. This allows students to better understand the building blocks and expand the knowledge acquired in the course by themselves afterward. Topics include UEFI architecture and programming, VT-x/EPT configuration, debugging tools, comparison of hypervisor designs, application of the technologies, and more.

This is a hands-on-oriented class. We believe that the students can learn and retain concepts and skills the best by working with those concepts by themselves and not by being taught; hence gaining the greatest value. With this philosophy, the class is designed for lab activities as the primary learning opportunities, and lectures are to explain backgrounds and the motivations for those. We will spend about 40% of the time for hands-on.

At the beginning of the class, students will receive skeleton implementations of our hypervisors and incrementally update them through the exercises with a clear understanding of motivations and design choices.

At the end of the class, students will also receive a full version of our hypervisor. This includes implementation of advanced concepts, such as stealth-hooking hypercall, use of VT-d, guest hardening (like HyperGuard if you are familiar with it), host hardening through CET, SMAP, UMIP, etc, handling of uncommon events like microcode update, NMI, and so on. This version can be used to complement your understanding of advanced topics and as a reference to explore more topics as you wish.

Additionally, a proof-of-concept implementation of taking and reverting to snapshots for fast full-system fuzzing will be shared as well.

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
