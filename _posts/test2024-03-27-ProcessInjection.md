---
title: Process Injection
date: 2024-03-27 14:28:00 +8000
categories: [Windows, AVBypass]
tags: [windows]     # TAG names should always be lowercase
author: alexis
---

# What is Process Injection

>As described by MITRE, process injection is a method of executing arbitrary code in the address space of a separate live process. Running code in the context of another process may allow access to the process's memory, system/network resources, and possibly elevated privileges. Execution via process injection may also evade detection from security products since the execution is masked under a legitimate process.

In other words, process injection is a technique commonly used by attackers to inject a malicious shellcode or payload inside the memory space of a running process. The type of payload we can run ranges from executing a random application such as `calc.exe` to a reverse shell.

