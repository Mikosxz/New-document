# Modern Operating Systems
	(Third Edition)

	by	Andrew S. Tanenbaum
		U. Vrije

## Preface

## About the author

# 1
## Introduction

	software
		^
		|	
	operating system
		^
		|
	hardware

Shell
GUI Graphical User Interface gooey

kernel mode	supervisor
user mode	web browser E-mail reader music player
		program that allow user to change password


## 1.1 what if an operating system?

## 1.1.1 the operating system as an extend machine

architecture: instruction, memory organization, I/O, bus structure

NEC PD765
16 command
reading && writing date, moving the disk arm, and formatting tracks,
initializing, sensing, resetting, and recalibrating the controller and the dirvers.

The job of the operating system is to create good abstractions and then implement and manage the abstract objects
thus created.

One of the  major tasks of the operating system is to hide the hardware and present programs with nice, clean,
elegant, consistent, abstractions to work with instead.

OS abstractions are same to applications, but application give user different user interface.

## 1.1.2 the  operating system as a resource manager

Modern operating system allow multiple programs to run at the same time.

In short, this view of the operating system holds that its primary task is to keep track of which programs are 
using which resource,

Resource management includes multiplexing(sharing) resources in two different ways: in time and in space.

Time: CPU
Space: memory, disk

## 1.2 history of operating system

## 1.2.1 the first generation(1945-55) vacuum tubes

The programmer insert plugboard into the computer,

By the early 1950s, the routine had improved somewhat with the introduction of puncheed cards.

## 1.2.2 the second generation(1955-65) transistors and batch system

The introduction of the transistor in the mid-1950s changed the picture radically.
For the first time, there was a clear separation between designers, builders, operators, programmers, and 
maintenance personnel.

These machines, now called mainframes,
To run a job(i.e, a program or set of programs), a programmer would first write the program on paper (in
FORTRAN or assembler), then punch it on cards. He would then bring the card deck down to the input room and
hand it to one of the operators and go drink coffee until the output was ready.
Much computer time was wasted while operators were walking around the machine room.

The batch system to reduce the wasted time.

$JOB, 10,6610802, MARVIN TANENBAUM

$FORTRAN 

Fortran program
///////////////
///////////////

$LOAD

$RUN

Data for program
//////////////
//////////////

$END

Large second-generation computers were used mostly for scientific and engineering calculations,

## 1.2.3 the third generation(1965-1980) ICs and multiprogramming

The IBM 360 was designed to handle both scientific(i.e., numerical) and commercial computing.
The IBM 360 was the first major computer line to use (small-scale) ICs (Integrated Circuits),

The intention was that all software, including the operating system OS/360 had to work on all models.

multiprogramming
On the 7094, when the current job paused to wait for a tape or other I/O operation to complete, the CPU simply 
sat idle until the I/O finished.
The solution that evolved was to partition memory into several pieces, with a different job in each partition,
While on job was waiting for I/O to complete, another job could be using the CPU.

Having multiple jobs safely in memory at once requires special hardware to protect each job against snooping and 
mischief by the other ones, but the 360 and other third-generation systems were equipped with this hardware.
Another major feature present in third-generation operating systems was the ability to read jobs from cards onto 
the disk as soon as they were brought to the computer room.
Then, whenever a running job finished, the operating system could load a new job from disk into the now-empty
partition and run it. This technique is called spooling (from Simultaneous Peripheral Operation On Line) and was 
also used for output.

The first general-purpose timesharing system, CTSS(Compatible Time Sharing System), was devoleped at M.I.T. on a 
specially modified 7094 (Corbato et al, 1962).

After the success of the CTSS system, M.I.T, Bell Labs, and General Electric(then a major computer manufacturer) 
decided to embark on the development of a "computer utility", a machine that would support some hundreds of 
simultaneous timesharing users. The designers of this system, known as MULTICS(MULTipled Information and Computer
Service), envisioned one huge machine providing computing power for everyone in the Boston area.

Another major development during the third generation was the phenomenal growth of minicomputer, starting with the
DEC PDP-1 in 1961.
One of the computer scientists at Bell Labs who had worked on the MULTICS project, Ken Thompson, subsequently found
a small PDP-7 minicomputer that no one using and set out to write a stripped-down, one-user version of MULTICS. This
work later developed into the UNIX operating system, which became popular in the academic world, with government 
agencies, and with many companies.

Two major versions developed, System V, from AT&T, and BSD(Berkeley Software Distribution) from the University of
California at Berkeley. These had minor variants as well. 
To make it possible to write programs that could run on any UNIX system, IEEE developed a standard for UNIX, called
POSIX, that most versions of UNIX now support.

As an aside, it is worth mentioning that in 1987, the author released a small clone of UNIX, called MINIX, for 
educational purposes.

The desire for a free production (as opposed to educational) version of MINIX led a Finnish student, Linus Torvalds,
to write Linux.

## 1.2.4 The Fourth Generation (1980-Present) Personal Computers

In 1974, when Intel came out with the 8080, the first general-purpose 8-bit CPU, it wanted an operating system for 
the 8080, in part to able to test it. 
Kildall then wrote a disk-based operating system called CP/M (Control Program for Microcomputers) for it.

In the early 1980s, IBM designed the IBM PC and looked around for software to run on it.
People from IBM contacted Bill Gates to license his BASIC interpreter.

When IBM came back, Gates realized that a local computer manufacturer, Seattle Computer Products, had a suitable 
operating system, DOS (Disk Operating System). 
IBM wanted certain modifications, so Gates hired the perpson who wrote DOS, Tim Paterson, as an employee of Gates'
fledgling company, Microsoft, to make them. The revised system was renamed MS-DOS (MicroSoft Disk Operating System)
and quickly came to dominate the IBM PC market. 

Engelbart invented the GUI(Graphical User Interface), complete with windows, icons menus, and mouse. These ideas
were adopted by researchers at Xerox PARC and incorporated into machines they built.

One day, Steve Jobs, who co-invented the Apple computer in his garage, visited PARC, saw a GUI, and instantly 
realized its potential value,

Windows NT (New Technology)

Windows Me (Millennium edition)

Windows XP (Windows 2000)

Windows Vista

nearly all UNIX systems support a windowing system called the X Window System (also known as X11) produced at M.I.T.
Often a complete GUI, such as Gnome or KDE is available to run on top of X11 giving UNIX a look and feel something
like the Macintosh or Microsoft Windows, for those UNIX users who want such a thing.

## 1.3 Computer Hardware Review

		Monitor			Keyboard		USB printer	Hard disk dirve
CPU	Memory	Video controller	Keyboard controller	USB controller	Hard disk controller
										
										bus
## 1.3.1 Processors

The "brain" of the computer is the CPU. It fetches instructions from memony and executes them.

Because accessing memony to get an instruction or data word takes much longer than executing an instruction, all
CPUs contain some registers inside to hold key variables and temporary results.

One of these is the *program counter*, which contains the memony address of the next instruction to be fetched.

Another register is the *stack pointer*, which points to the top of the current stack in memony. The stack contains
one frame for each procedure that has been entered but not yet exited.

Yet another register is the *PSW(Program Status Word)*. The register contains the condition ocde bits, which are
set by comparison instructions, the CPU priority, the mode(user or kernel), and various other control bits.

Many modern CPUs have facilities for executing more than one instructions at the same time.
Such an organization is called a pipeline,

Even more advanced than a pipeline design is a superscalar CPU, shown in Fig. 1-7(b).
In this design, multiple execution units are present, for example, one for integer arithmetic, one for floating-
point arithmetic, and one for Boolean operations.

An implication of this design is that program instructions are often executed out of order.

Most CPUs, except very simple ones used in embedded systems, have two modes, kernel mode and user mode, as mentioned
earlier.
When running in kernel mode, the CPU can execute every instruction in its instruction set and use every feature of
the complete hardware.
In contrast, user programs run in user mode, which permits only a subset of the instructions to be executed and a
subset of the features to be accessed.

To obtain services from the operating system, a user program must make a system call, which traps into ht kernel
and invokes the operating system.

Multithreaded and Multicore Chips

The abundance of transistors is leading to a problem: what to do with all of them? We saw one approach above:
superscalar architectures, with multiple functional units.

The obvious next step is to replicate not only the functional units, but also some of the control logic.
The Pentium 4 and some ohter CPU chips have this property, called multithreading or hyperthreading
(Intel's name for it).

For example, if one of the processes needs to read a word from memony(which takes many clock cycles), a 
multithread CPU can just switch to another thread. Multithreading does not offer true parallelism. Only
one process at a time is running, but thread switching time is reduced to the order of a nanosecond.

Beyond multithreading, we have CPU chips with two or four or more complete processors or cores on them.

## 1.3.2 Memory

The memory system is constructed as a hierarchy, and greater cost per bit than the lower ones, ofter by factors
of a billion or more.

|Typical access time|Memorys|Typical capacity|
|:-|:-:|-:|
|1 nsec|Registers|<1KB|
|2 nsec|Cache|4MB|
|10 nsec|Main Memory|512-2048MB|
|10 msec|Magnetic disk|200-1000GB|
|100 sec|Magnetic tape|400-800GB|

Main memory usually called RAM(Random Access Memory).
ROM(Read Only Memory) is programmed at the factory and cannot be changed afterward.

EEPROM(Electrically Erasable PROM) and flash memory are also nonvolatile, but in contrast to ROM can be erased
and rewritten.

Yet another kind of memory is CMOS, which is volatile.

## 1.3.3 Disks

## 1.3.4 Tapes

## 1.3.5 I/O Devices


