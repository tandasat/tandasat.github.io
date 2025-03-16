# Hypervisor Development for Security Researchers on the Intel Platform

- [Hypervisor Development for Security Researchers on the Intel Platform](#hypervisor-development-for-security-researchers-on-the-intel-platform)
  - [Overview](#overview)
  - [Target Audience](#target-audience)
  - [Prerequisites](#prerequisites)
  - [Outline](#outline)
  - [Details](#details)
  - [Pricing](#pricing)
  - [Format and Package](#format-and-package)
  - [Hardware and Software Requirements](#hardware-and-software-requirements)
  - [Registration and Contacts](#registration-and-contacts)


## Overview

This class teaches you how hypervisors and hardware-assisted virtualization technologies work. You can use this knowledge to build your hacking hypervisors for research and to study, customize, and break existing hypervisors.

We achieve this by developing lightweight, UEFI module-based hypervisors using Intel VT-x and analyzing various advanced hypervisor applications, such as fuzzing and system hardening. The knowledge we acquire can be applied to kernel module-based hypervisors and AMD processors.

The class is hands-on oriented; we will spend 30-40% of the time with excesses.

📝 Concerned about the timezone? No worries. You will receive materials beforehand and a recording after each day and are encouraged to ask questions even before and after the period of the class. See [Format and Package](#format-and-package) for more details.


## Target Audience

Software developers, security researchers, and anyone interested in expanding their knowledge of virtualization technologies, the x86_64 system architecture, and UEFI should attend the class. Many past students enjoyed discovering details of new system architecture aside from learning Intel VT-x!


## Prerequisites

Required:
- Fluency in C or Rust🦀
- Familiarity with the x86_64 architecture, such as privilege levels, interrupts, page tables, and system registers at the concept level.
- Experience in system programming, such as kernel-module development, is a plus but not a requirement.
- Familiarity with UEFI is NOT needed.

You will receive links to recommended pre-class learning materials 2-3 weeks before the class.


## Outline

1. Hypervisor designs and UEFI
    - Lectures: various use of hypervisors, UEFI module-based hypervisors, comparison with kernel module-based hypervisors, and UEFI/EDK2

2. VT-x Basics
    - Lectures: processor modes, VMCS, host vs. guest, VM-exit/-entry, high-level design options, tools and techniques to diagnose bugs, and how to navigate specifications
    - Lab: source-level debugging with VMware
    - Lab: configuring and starting host and guest, monitoring CPUID execution
    - Lab: troubleshooting VMX instruction errors with Bochs

3. OS Boot
    - Lectures: system boot phases, boot time vs runtime, physical vs virtual mode, and UEFI runtime drivers
    - Lab: controlling VM-exits with MSR bitmaps
    - Lab: booting Windows and separating resources between guest and host
    - Lab: tracing guest page faults with exception interception and event injection
    - Advanced lectures and demos: analysis of Hyper-V configurations and common vulnerabilities in pass-through hypervisors

4. Extended Page Tables (EPT)
    - Lectures: traditional x64 address translation vs EPT-enabled translation, EPT setup and activation, EPT-induced VM-exits
    - Lab: building and enabling pass-through EPT
    - Lab: tracing guest execution with EPT
    - Advanced lectures and demos: VPID, caches invalidation, stealth hooking with EPT, Snapshot-based fuzzing hypervisors, memory types emulation, device virtualization and VT-d (IOMMU/DMA remapping)

5. Multi-processors Support
    - Lectures: multi-processor protocol, processor activity state, application processors startup, unrestricted guest, Hypervisor Top Level Functional Specification (TLFS), and enlightenment
    - Lab: virtualizing all processors
    - Lab: booting multi-processor Windows by emulating INIT-SIPI-SIPI

6. Control Register Shadowing
    - Lectures: control register guest/host mask, read shadow VMCS, and complexities with emulation of control register access
    - Lab: booting Ubuntu by properly emulating MOV-to-CRx

7. Additional Demos and Resources
    - MBEC, VT-rp (HLAT), nested virtualization techniques (software-based, VMCS shadowing, enlightened VMCS, EPT virtualization strategies), Intel TXT and PPAM, hardware debuggers (DCI), and helpful open source projects

Contents may change in a way that does not impact the learning objectives.


## Details

Virtualization technologies are critical components in software security and analysis. How can hypervisors be used to secure system software? How can custom hypervisors be written to perform reverse engineering and fuzzing more efficiently?

This class will teach you the foundation to answer those questions by developing simple hypervisors together! The class is designed so everything is built from scratch and optimized for learning. This allows you to understand the building blocks of real-world applications of virtualization technologies and expand the knowledge for your interests afterward.

This class is hands-on oriented. We believe that we can learn and retain knowledge best by tackling concrete challenges rather than being taught. With this philosophy, the class is designed with lab activities as the primary learning opportunities and lectures to explain the theories behind them. We will spend 30-40% of the time on hands-on exercises.

At the beginning of the class, you will receive a skeleton implementation of a hypervisor and incrementally update it through a series of exercises. We will also discuss other design options to understand their pros and cons.

As we learn foundations, we will analyze various applications and their implementations. This includes snapshot-based system-level fuzzing, performant system hardening with MBEC and HLAT (VT-rp), HVCI, and KDP on Windows, dynamic analysis with stealth hooking, and SMM security reporting with Intel TXT (PPAM).

You will also be introduced to two additional hypervisor implementations as references:

- The cross-platform version in Rust🦀 This version supports Intel and AMD processors and compiles into a UEFI module and Windows driver. This is an excellent reference for when you review the "must do" parts and rebuild your hypervisor from scratch for AMD or as a Windows driver, or simply prefer the Rust programming language.

- The full version of our hypervisor. This includes the implementation of advanced concepts, such as stealth-hooking hypercall, use of VT-d (DMA protection), guest hardening, host hardening with CET, SMAP, and UMIP, and handling of uncommon events like microcode update, NMI, and MTRR updates. This version can complement your understanding of advanced topics and be a reference to explore more as you wish.

![Hypervisor_Development_for_Security_Researchers.png](/Images/Hypervisor_Development_for_Security_Researchers.png)


## Pricing

📝 This information is for remote offerings.

| Type       | Individual | Company  |
| ---------- | ---------- | -------- |
| Early Bird | 2970 USD   | 3780 USD |
| Standard   | 3300 USD   | 4200 USD |

All prices are per seat. Including tax.

- Early Bird: We offer a 10% discount if registration is made 60 days before the first day of the class.
- Individual vs Company: We price the class differently depending on whether it is paid by your employer or yourself.
- We may offer a 50% discount for full-time, unemployed school students. Contact us before registration and payment.
- We refund 100% (minus any fees incurred by our payment platform and your bank) on cancellation notified 14 days before the first day of the class. Cancellation within 14 days is not refundable.


## Format and Package

Format:
- The course is offered in either the remote or in-person format, in live sessions.
  - No pre-recorded course is offered.

Package:
- Material
  - Course materials (slides and sample code) will be shared 2-3 weeks before the class.
  - Recording will be available shortly after the end of each day.
- Support
  - 3 weeks of asynchronous consultation on Slack and email from the last day of the class.
  - The indefinite right to request the latest slides and code for no additional cost.

📝 It is perfectly fine to start learning yourself earlier, skip live sessions, watch recordings, and ask questions asynchronously at your own pace by taking advantage of the package. One of past students did this and successfully developed his hypervisor from scratch! The trainer is here for you to learn in any reasonable style that works for both of us.


## Hardware and Software Requirements

You need to have the following hardware and software:

- The host machines with the Intel processors, SSD, 8GB+ RAM and 50GB+ of free storage space
- For Windows users
    - Windows 11 without Virtualization-based Security (VBS)
    - Ubuntu 22.04+ on WSL version 1
    - VMware Workstation Pro 17
- For Linux users
    - Ubuntu 22.04+
    - VMware Workstation Pro 17
- For macOS users
    - macOS 15
    - VMWare Fusion Pro 13

📝 An Intel processor-based machine is required.

Newer operating systems and software are supported. Older software and another Linux distro may be workable but not tested. Other hypervisors, such as KVM, Hyper-V, or VirtualBox, cannot be used. If the host machine cannot be arranged locally, it can also be a cloud-provided machine. Contact the trainer for suggestions if you need a cloud-provided machine.

You will receive setup instructions 2-3 weeks before the class and must complete them before the class.


## Registration and Contacts

- For the dates of the next public class, see [the top page](README.md).
- To receive updates on future public classes, subscribe to [our mailing list](https://groups.io/g/system-programming-lab) by sending an empty email to [system-programming-lab+subscribe@groups.io](mailto:system-programming-lab+subscribe@groups.io?subject=Subscribe%20Request).
- For further inquiries, contact us: [email](mailto:tanda.sat@gmail.com?subject=Hypervisor%20Development%20for%20Security%20Researchers), [X](https://x.com/standa_t), [Mastdon](https://infosec.exchange/@satoshi_tanda), [Bluesky](https://satoshi-tanda.bsky.social/).
