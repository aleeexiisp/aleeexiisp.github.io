---
title: Windows Memory
date: 2024-03-27 14:25:00 +8000
categories: [Windows, Memory]
tags: [windows, Memory]     # TAG names should always be lowercase
author: alexis
---

# How does the Windows Memory work ?

Everybody knows what the RAM memory is, but how does it work ? In general, computer processors (CPU) are constantly making read and write operations. If this was done on the disk (SSD or HDD) constantly the computer would be very slow. That is why an intermediate place to store data was required.

Memory is a physical storage used by CPUs to store data that is constantly read. This memory is temporary and is always loaded on each boot. 

Let's first delve into the whole process of memory usage from boot to running the user context to properly understand it. Bear in mind that I will be explaining all complex concepts at the beggining of each section so that everything is made clearer. 

To begin with, in order to understand memory, it is important to make clear where does it start. How the computers use memory to boot and start ?

## 2. What is the Memory ?

Computers essentially work by making multiple read and write operations. For that reason, they need some place to work with that data. This is usually done on the register I mentioned before as they are very quick and efficient although that is the most granual way of speaking about memory. If we go back a bit we realise that computers can manage big chunks of data such as huge videogames, coding applications, etc. They must be stored somewhere, this is known as `Non-Volatile` memory from which we highlight the Solid-state drive (SSD) or the Hard-disk drive (HDD). However, if the computer only used these sort of disks, the operations the application had to do would be very inefficient and heavy weight. 

At this point the computers needed an intermediate Volatile memory in where they could store the running processes temporarily and execute them from that place. That would make the whole running of the application faster. 

## 3. 









