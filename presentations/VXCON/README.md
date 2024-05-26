# Hypervisor Development Hands On for Security Researchers on Windows

## Abstract

In this workshop, you will learn the basics of how VT-x by carefully analyzing and debugging source code of a minimalistic hypervisor on Windows. After this workshop, you will understand how to turn on/off virtualization from ring-0 code, trap execution of certain instructions in the system, and more importantly, learn how to extend what you studied by yourself.

## Caveats

**This workshop is a hands-on style**. You are must bring a laptop and complete set up instructions as specified below **prior to the workshop**:

- [Environment Setup](Contents/Environment_Setup.md)

The trainer will partially be available for assisting set up an hour prior to the workshop, but please ask questions at [@standa_t](https://twitter.com/standa_t) prior to it if you have any questions.

## Contents

(Any of those contents may change)

### Introduction

- Goals and Non-Goals
- Review of Prerequisites Specifics
- Terminology

### Basics of Intel VT-x

- Processor Modes: VMX root operation and VMX non-root operation
- Mode Transition: VMX instructions, VM-exit and VM-entry
- VMCS: A Context Structure for a Guest
- Source Code Work-through
- Exercise 1: Implement the CPUID Handler

### Customizing Hypervisor

- More on VMCS
- Opting-in More VM-exit
- Exercise 2: Implement a Context Switch Tracer (CR3 monitor)

### Wrapping Up

- Typical Vulnerabilities You Would Make
- Further Features and Learning Resources