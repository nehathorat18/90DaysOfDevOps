
> **Key Points:**
> - Everything in Linux is either a file or a directory.
> - Everything in Linux is a process.

## Core Components of Linux (Kernel, User Space, Init/systemd)

### Kernel
Kernel is the heart of Linux, meaning the core component which only interacts with hardware.

### User Space
User space is a protected memory area where all non-kernel user programs, applications and most system libraries execute with limited privileges.

### Init / systemd
When we start any Linux machine, the first process that runs is called init, and it runs as PID 1. A system daemon is any process that runs in the background. We can check the status of processes using systemd.

---

## How Processes Are Created and Managed

When we start a system by pressing the power-on button, the BIOS on the motherboard is triggered and initializes the hardware. The Linux kernel is then loaded, and GNU GRUB starts the computer and loads Linux, after which the Ubuntu loading screen appears. During this process, a background process starts called init, which runs as PID 1.

---

## What systemd Does and Why It Matters

systemd is basically a system daemon that runs background processes. It manages everything from hardware devices to network connections, controls when programs run and even handles system logs.

---

## Explain Process States (running, sleeping, zombie, etc.)

| STAT Value | Meaning | Description |
|-----------|--------|------------|
| R | Running | A process that is currently running or ready to run |
| S | Sleeping | A process waiting for input or an event |
| D | Uninterruptible sleep | A process waiting for I/O (disk/network) |
| Z | Zombie | A process that has finished execution but still exists |
| T | Stopped | A process that has been manually paused |

---

## List 5 commands you would use daily

- ls  
- cd  
- grep  
- ps  
- sudo  
