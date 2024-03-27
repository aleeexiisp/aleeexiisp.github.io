---
title: Booting Process
date: 2024-03-27 14:25:00 +8000
categories: [Windows, Boot]
tags: [windows, Boot]     # TAG names should always be lowercase
author: alexis
---

# What is the booting process ?



## 1. Booting Process

>`Basic Input/Output System (BIOS)` or `Unified Extensible Firmware Interface (UEFI)` main function is to initialise the hardware components and start the Operating System. The firmware then takes care of configuring and ensuring a proper hardware state. RAM, Disks, motherboard, graphics card.

`Booting` is the process of switching the computer ON and starting the operating system. The proces, consists in 6 steps:

1. BIOS and Program Setup
2. Power-On-Self-Test (POST)
3. Operating System Load
4. Boot Loader Execution
5. Kernel Initialisation
6. Logon/Graphical Interface

The following process describes how the BIOS Legacy works. On modern systems, UEFI is utilised and uses different techniques to provide a more secure and efficient boot. I will start explaning BIOS and will expand with UEFI.

### 1.1 Basic Input/Output System (BIOS)

>A `REGISTER` is a physical component of CPUs that are small and are intended for fast storage. They are used to store operands, intermediate results, memory addresses and other data required by the CPU. They are crutial to execute instructions efficiently. (Arithmetic instructions)

>A `CPU runs instructions sequentially`, i.e. first moving one value to a register, then adding 1 to that register, etc.

>`JUMP` is an assembly instruction that lets the CPU/program know the place from which needs to start reading instructions. If some code I want to execute starts in 0xFFFF10 and the CPU is currently executing instructions sequentially at 0x120321, if the next instruction is a JUMP 0xFFFF10, the CPU will start running instructions at that memory address.

>`Read-Only Memory (ROM)` is a non-volatile memory, which means that it retains its contents even when power is turned off. It is a physical chip that is commonly found on motherboards. They contain firmware or instructions that are essential for booting up the system and performing basic input/output operations. This memory and can only be written once and is then read-only.

>A `Boot Loader` is a small program that resides in the system's firmware or in a dedicated boot partition. Its primary function is to load the Operating System into memory and start its execution. It handles the transition from the firmware's execution to the operating system's execution.

#### 1. BIOS and Pogram Setup

1. When the computer is first started, the CPU executes a harcoded JUMP instruction from a CPU register. 
2. The CPU jumps to a predefined memory location in the `Read-Only Memory (ROM)`
3. The CPU starts executing the BIOS/UEFI directly from the ROM.

#### 2. Power-On-Self-Test (POST)

1. The BIOS runs a power-on self-test (POST) to check and initialise required devices such as main memory (DRAM), the CPU, the PCI bus and the PCI devices...

#### 3. Operating System Load

1. If the POST succeeds, the BIOS loads an MBR Partition Table into the RAM.
2. The BIOS then goes through a pre-configured list of non-volatile storage devices until finds one that is bootable.
3. Typically the primary boot device is the internal Hard Drive or SSD, where the OS is installed.

#### 4. Boot Loader Execution

1. The boot loader, such as the Windows Boot Manager (bootmgr), is loaded from the designated boot device into memory.
2. Once it is executed, it loads the Windows kernel (ntoskrnl.exe) into RAM memory and hands over the control.
3. The kernel initialises the Windows executive subsystem and other core components required for the operating system to function.

#### 5. Kernel Initialisation

1. The Windows Kernel initialises various `system services`, drivers, and components necessary for system operation.
2. Sets up memory management, initialises hardware drivers, and prepares the system for user interaction.

#### 6. Logon/Graphical Interface

1. The Graphical User Interface (GUI) or login screen is presented to the user.
2. Authentication is required and the Windows Desktop Environment is loaded.

![Desktop View](./assets/img/WindowsMemory/BIOS.jpg){: .center}

### 1.2 Unified Extensible Firmware Interface (UEFI)

#### 1. UEFI Initialisation

1. When the computer is turned ON, the UEFI firmware initialises.
2. UEFI firmware performs various initialisation tasks, such as detecting and initialising hardware components, configuring system settings, and setting up the boot environment.

#### 2. Boot Device Selection

1. The UEFI firmware locates and prioritises bootable devices based on the boot order configured in the UEFI settings.
2. Bootable devices include internal storage drives (HDDs/SSDs), external storage devices, optical drives, and network boot options.

#### 3. Boot Loader Execution

1. UEFI firmware loads the boot loader specified in the boot order.
2. The boot loader, often the Windows Boot Manager (bootmgfw.efi) for Windows systems, or GRUB for Linux systems, is responsible for loading the operating system kernel and initiating the boot process.

#### 4. Operating System Loading

1. Once the boot loader is executed, it loads the operating system kernel (e.g., Windows kernel, Linux kernel) into memory.
2. The kernel initialises the operating system, sets up device drivers, and prepares the system for user interaction.

#### 5. Graphical Interface or Logon

1. Finally, the operating system presents the graphical user interface (GUI) or login screen to the user.
2. If user authentication is required, the user logs in with their credentials.
3. Once logged in, the desktop environment or user interface is loaded, and the user can start using the operating system.

![Desktop View](./assets/img/WindowsMemory/UEFI.jpg){: .center}











