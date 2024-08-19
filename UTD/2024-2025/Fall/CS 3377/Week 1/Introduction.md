## Course
- Work will be done in C
- access control
- threads
- shell scripts
- networking (sockets, etc)
- version control (git)
- Cloud
- REGEX

## What is UNIX?
Unix is an operating system developed by AT&T Bell Labs in the 1960's.
- CLI
- GUIs are now available
- Predecessor to Linux
- Mac is also a Unix based system
- Linux is open source!
	- Free
	- customizable
	- stable
	- Ideal OS for scientists, researchers, and programmers
### What is an Operating System?
- Allows communication between hardware components in machine
- Controls hardware
- Runs applications
- Manages data and files
## Features
- Portable
	- Supports multiple architectures
- Multitasking
- Multi-user
- Written in C
- Unix shell
- Includes support for regular expressions
- hierarchical file system
  
## Architecture
- Kernel: Schedules programs
	- Manages data and files, storage, etc
	- performs all hardware access
- Init: First program run by kernel on boot
- Shell: Presents each user a prompt:
	- Interprets commands
	- Executes commands
	- Provides environment
From APUE Textbook:
"In a strict sense, an operating system can be defined as the software that controls the hardware resources of the computer and provides an environment under which programs can run. Generally, we call this software the kernel, since it is relatively small and resides at the core of the environment. Figure 1.1 shows a diagram of the UNIX System architecture. The interface to the kernel is a layer of software called the system calls (the shaded portion in Figure 1.1). Libraries of common functions are built on top of the system call interface, but applications are free to use both. (We talk more about system calls and library functions in Section 1.11.) The shell is a special application that provides an interface for running other applications.

In a broad sense, an operating system consists of the kernel and all the other software that makes a computer useful and gives the computer its personality. This other software includes system utilities, applications, shells, libraries of common functions, and so on.

For example, Linux is the kernel used by the GNU operating system. Some people refer to this combination as the GNU/Linux operating system, but it is more commonly referred to as simply Linux. Although this usage may not be correct in a strict sense, it is understandable, given the dual meaning of the phrase operating system. (It also has the advantage of being more succinct.)"


## File System


#CS #cs3377 #utd 