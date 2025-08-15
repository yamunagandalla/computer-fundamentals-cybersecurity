# Operating System: Processes for Cybersecurity
This repository contains beginner-friendly notes on **Processes in Operating Systems**, specially focused on cybersecurity learners.  
Understanding processes is fundamental for ethical hacking, malware analysis, and system security.

## Table of Contents
1. [What is a Process?](#what-is-a-process)
2. [How a Program Becomes a Process](#how-a-program-becomes-a-process)
3. [Process States](#process-states)
4. [Context Switching](#context-switching)
5. [Parent & Child Processes](#parent--child-processes)
6. [Process Scheduling Basics](#process-scheduling-basics)
7. [Linux Commands for Process Investigation](#linux-commands-for-process-investigation)
8. [Next Steps](#next-steps)
9. [License](#license)
10. [Author](#author)

---

## 1. What is a Process?
A **process** is a program in execution.  

- A program is just a set of instructions stored on disk.  
- When executed, it becomes an active entity called a **process**.  
- A single program can create multiple processes if run multiple times (e.g., opening a `.exe` file multiple times).

**Cybersecurity relevance:** Attackers often manipulate or monitor processes to hide malware or maintain persistence.

---

## 2. How a Program Becomes a Process

### i) Writing the Program
- Code is written in languages like C, Python, Java.  
- Saved as a file on the hard disk.  
- At this stage, it is just a program, not active.

### ii) Request to Run
- User asks the OS to execute the program.  
- OS copies the executable into RAM for CPU execution.

### iii) Loading into RAM
- CPU can execute instructions only from RAM, so the OS loads the program there.

### iv) Creating a Process Control Block (PCB)
The **PCB** is a data structure that stores:

- **Process ID (PID)** – Unique number for the process  
- **Program Counter (PC)** – Address of the next instruction  
- **CPU Registers** – Temporary storage for variables during execution  
- **Memory Locations Used** – Code, data, stack segments  
- **State** – Ready, Running, Waiting, Terminated

### v) Example Code
```c
#include <stdio.h>
int main() {
    int a = 5, b = 3;
    int sum = a + b;
    printf("Sum = %d\n", sum);
    return 0;
}
Cybersecurity relevance: Understanding PCB structure helps detect malicious processes and analyze malware behavior.

3. Process States

Typical states a process goes through:

New → Ready → Running → Waiting → Ready → Terminated


Cybersecurity relevance: Malware may stay in “waiting” or “ready” states to evade detection.

4. Context Switching

OS switches between processes by saving and loading PCBs.

Poorly managed context switches can be exploited to escalate privileges.

5. Parent & Child Processes

Every process is created by another process (parent).

Example in Linux:

ps -ef --forest


Cybersecurity relevance: Malware may spawn hidden child processes to run in the background.

6. Process Scheduling Basics

OS decides which process runs using algorithms like Round Robin or Priority Scheduling.

Attackers can abuse high-priority processes to consume system resources (DoS attacks).

7. Linux Commands for Process Investigation
Command	Purpose
ps aux	List all processes
top / htop	Monitor processes in real-time
pidof <name>	Find process ID
kill <PID>	Terminate a process
lsof -p <PID>	View files used by a process
strace -p <PID>	Trace system calls of a process
Next Steps

Once comfortable with processes, explore:

System calls and kernel interactions

Process security and malware detection

Linux process management tools like htop, lsof, strace

Threading and multithreading concepts

License

This content is open-source and free to use under the MIT License.

Author

Created by Yamuna Gandalla – a beginner in cybersecurity with a mission to learn and share.
