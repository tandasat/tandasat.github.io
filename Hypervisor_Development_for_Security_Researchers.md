# Hypervisor Development for Security Researchers on the Intel Platform

- [Hypervisor Development for Security Researchers on the Intel Platform](#hypervisor-development-for-security-researchers-on-the-intel-platform)
  - [Overview](#overview)
  - [Audiences](#audiences)
  - [Level](#level)
  - [Prerequisites](#prerequisites)
  - [Learning Objectives](#learning-objectives)
  - [Outline](#outline)
  - [Details](#details)
  - [Pricing](#pricing)
  - [Format and Package](#format-and-package)
  - [Hardware and Software Requirements](#hardware-and-software-requirements)
  - [Registration and Contacts](#registration-and-contacts)


## Overview

This course helps you gain the skills and knowledge to develop lightweight hypervisors as UEFI modules using Intel VT-x. This is a hands-on heavy class, and we will spend about 40% of the time with excesses.

In addition to the live sessions, you will receive materials beforehand and a recording after each day, and can ask questions asynchronously even after the period of the class. This is particularly helpful for those with challenging time zone differences (see [Format and Package](#format-and-package) for more details).


## Audiences

This class is geared towards software developers, security researchers, and those interested in expanding their knowledge of Intel VT-x, the x86_64 system architecture, and/or UEFI.


## Level

- Intermediate to advanced


## Prerequisites

Required:
- Strong experience in C (or C++) programming.
- Familiarity with the x86_64 architecture, such as privilege levels, interrupts, page tables, and system registers.
- System programming experience, such as kernel-module development, is a plus but not a requirement.

We will introduce recommended pre-class learning materials about 3 weeks prior to the class.


## Learning Objectives

At the end of the class, you will gain enough knowledge and skills to develop your pass-through hypervisors. Covered topics include but are not limited to:

- Key concepts of VT-x and programming interfaces
- Various applications of hypervisors in the real world and their implementations, examples include:
  - System hardening, such as HVCI and KDP on Windows
  - System-level fuzzing, such as What The Fuzz
  - System-level inspection and rootkit, such as antivirus hypervisors
- Vulnerabilities in some of the above types of hypervisors
- Early OS boot activities and handling of them as a hypervisor
- Subtle yet complex concepts such as control register access, memory types, cache invalidation, and emulation of those
- Basic UEFI-module development workflow, tools and techniques


## Outline

1. Hypervisor and UEFI
    - Lectures: various use of hypervisors, UEFI module-based hypervisors, comparison with kernel module-based hypervisors, and UEFI/EDK2

2. VT-x Basics
    - Lectures: processor modes, VMCS, "host" vs "guest", VM-exit, VM-entry, and high-level design options
    - Lab: source-level debugging with VMware
    - Lab: configuring and starting host and guest, monitoring CPUID execution
    - Lab: troubleshooting VMX instruction errors with Bochs

3. OS Boot
    - Lectures: system boot phases, boot time vs runtime, physical vs virtual mode, and runtime drivers for monitoring OS activities
    - Lab: controlling VM-exits with MSR bitmaps
    - Lab: booting Windows and isolating resources between guest and host
    - Lab: tracing guest page faults with exception interception and event injection
    - Advanced lectures and demos: analysis of Hyper-V configurations and common vulnerabilities in pass-through hypervisors

4. Extended Page Tables (EPT)
    - Lectures: traditional x64 address translation vs EPT-enabled translation, EPT setup and activation, EPT-induced VM-exits
    - Lab: building and enabling pass-through EPT
    - Lab: tracing guest execution with EPT
    - Advanced lectures and demos: memory types emulation, caches invalidation, VPID, stealth hooking with EPT, MBEC, VT-rp (HLAT), device virtualization and VT-d (IOMMU/DMA remapping)

5. Multi-processors Support
    - Lectures: multi-processor protocol, processor activity state, application processors startup, unrestricted guest, Hypervisor Top Level Functional Specification (TLFS) and enlightenment
    - Lab: virtualizing all processors
    - Lab: booting multi-processor Windows by emulating INIT-SIPI-SIPI

6. Control Register Shadowing
    - Lectures: control register guest/host mask, read shadow VMCS, and complexities with emulation of control register access
    - Lab: booting Ubuntu by properly emulating MOV-to-CRx

7. Demos and References
    - Nested virtualization (software-based, VMCS shadowing, enlightened VMCS, EPT virtualization strategies), snapshot-based fuzzing hypervisors, PPAM, hardware debuggers (DCI), single board computers, and relevant open source projects

Contents may change in a way that does not impact the learning objectives.


## Details

A hypervisor is a critical component in cloud computing, and there is also an increasing interest in applying virtualization technologies in software security and analysis. How can hypervisors be used to secure system software? How to write custom hypervisors to perform reverse engineering and fuzzing more efficiently?

In this class, you will have the answers to those questions by developing simple hypervisors together. The class is designed in a way such that everything is built from scratch and optimized for learning. This allows you to better understand the building blocks of real-world applied use of virtualization technologies and expand the knowledge for their interests afterward.

This is a hands-on-oriented class. We believe that we can learn and retain knowledge best by tackling concrete challenges and not by being taught. With this philosophy, the class is designed for lab activities as the primary learning opportunities, and lectures are to explain the theories behind them. We will spend about 40% of the time on hands-on exercises.

At the beginning of the class, you will receive a skeleton implementation of a hypervisor and incrementally update it through a series of exercises along with discussions of other design options to understand the pros and cons.

As we learn concepts, we will discuss various applications of virtualization technologies and their implementations. This includes snapshot-based system-level fuzzing, performant system hardening with MBEC and HLAT (VT-rp), eg, HyperGuard, HVCI and KDP on Windows, dynamic analysis with stealth-hooking, and SMM security reporting (PPAM).

Additionally, you will receive a full version of our hypervisor. This includes the implementation of advanced concepts, such as stealth-hooking hypercall, use of VT-d (DMA protection), guest hardening, host hardening with CET, SMAP, and UMIP, and handling of uncommon events like microcode update, NMI, and MTRR updates. This version can complement your understanding of advanced topics and be a reference to explore more as you wish.

![Hypervisor_Development_for_Security_Researchers.png](/Images/Hypervisor_Development_for_Security_Researchers.png)


## Pricing

| Type       | Individual | Company  |
| ---------- | ---------- | -------- |
| Early Bird | 2700 USD   | 3600 USD |
| Standard   | 3000 USD   | 4000 USD |

All prices are per seat.

- Early Bird: We offer a 10% discount if registration is made 60 days before the first day of the class.
- Individual vs Company: We price the class differently depending on whether it is paid by your employer or yourself.
- We may offer a 50% discount for full-time, unemployed school students. Contact us before registration and payment.
- We refund 100% (minus any fees incurred by our payment platform and your bank) on cancellation notified 7 days before the first day of the class. Cancellation within 7 days is not refundable.


## Format and Package

Format:
- The training is offered remotely through Zoom.

Package:
- Material
  - Training materials (slides and sample code) will be shared 3 weeks prior to the class.
  - Recording will be available shortly after the end of each day.
- Support
  - 3 weeks of asynchronous consultation on Slack and email from the last day of the class.
  - The Indefinite right to request the latest slides and code for no additional cost.

📝 It is perfectly fine to start learning yourself earlier, skip live sessions, watch recordings, and ask questions asynchronously at your own pace by taking advantage of the package. One of past students did this and successfully developed his hypervisor from scratch! The trainer is here for you to learn in any reasonable style that works for both of us.


## Hardware and Software Requirements

You are expected to have the following hardware and software:

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

The newer versions of the operating systems and other software are supported. Older versions of software and another Linux distro may be workable but not tested. Other hypervisors such as KVM, Hyper-V, or VirtualBox cannot be used.

The host system can also be a cloud-provided machine if the host machine cannot be arranged locally. Those are confirmed to be usable:
- Scaleway's Intel [Elastic Metal Servers](https://www.scaleway.com/en/pricing/#elastic-metal) for a Linux host, and
- Amazon's Intel bare metal server [m5zn.metal](https://aws.amazon.com/ec2/pricing/on-demand/) for a Windows host

Contact us for suggestions if you need a cloud-provided machine.

You are expected to complete the setup instructions that will be sent by the instructor before the class.


## Registration and Contacts

- For the dates of the next public class, see [the top page](README.md).
- To receive updates on future public classes, subscribe to [our mailing list](https://groups.io/g/system-programming-lab) by sending an empty email to [system-programming-lab+subscribe@groups.io](mailto:system-programming-lab+subscribe@groups.io?subject=Subscribe%20Request).
- For further inquiries, reach out to [@standa_t](https://twitter.com/standa_t) on X (Twitter) or [send us an email](mailto:tanda.sat@gmail.com?subject=Hypervisor%20Development%20for%20Security%20Researchers). e also offer a private class with a minimum of 8 people. Please contact us to discuss further details.
