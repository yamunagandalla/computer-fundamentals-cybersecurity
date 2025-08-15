PROCESS IN OPERATING SYSTEM – NOTES
1. WHAT IS PROCESS IN OPERATING SYSTEM?

A process is a program in execution. For example, when we write a program in C or C++ and compile it, the compiler creates binary code. The original code and binary code are both programs. When we actually run the binary code, it becomes a process.

A process is an active entity instead of a program, which is considered a passive entity.
A single program can create many processes when run multiple times; for example, when we open a .exe or binary file multiple times, multiple instances begin (multiple processes are created).

2. How a Program Becomes a Process?

i) Writing the Program
First, you write some code (C, Python, Java, anything).
This code is saved as a file in your hard disk (storage).
At this stage, it’s just dead code — it’s not doing anything.
We call it a program.

ii) Request to Run the Program
When you want to run it, you click Run or type a command in the terminal.
You’re basically telling the Operating System (OS):
"Hey, please run this code for me."

iii) Loading into RAM
The OS copies the executable from the hard disk into RAM (primary memory).
This is because the CPU can only execute instructions from RAM, not directly from the disk.

iv) Creating a Process Control Block (PCB)
The OS creates a PCB (Process Control Block) — a data structure that stores:

Process ID (PID)

Program counter (address of the next instruction)

CPU registers

Memory locations used

State (Ready, Running, etc.)

v) Example Code
#include <stdio.h>
int main() {
    int a = 5, b = 3;
    int sum = a + b;
    printf("Sum = %d\n", sum);
    return 0;
}


a) When OS creates the PCB:

Process ID (PID) – Unique number given by the OS when the process starts.

Program Counter (PC) – Holds the address of the next instruction.

CPU Registers – Temporary storage for variables during execution.

Memory Locations Used – Code, Data, Stack segments.

State – Ready, Running, Waiting, Terminated.

Extra Cybersecurity-Relevant Additions

3. Process States Diagram

New → Ready → Running → Waiting → Ready → Terminated


Helps in detecting suspicious behavior like malware staying in “waiting” to avoid detection.

4. Context Switching
When switching between processes, the OS saves the current process’s PCB and loads another’s.
Attackers may exploit poorly managed context switches to gain higher privileges.

5. Parent & Child Processes
Every process is created by another process (parent).
Example in Linux:

ps -ef --forest


Malware often spawns hidden child processes to run in the background.

6. Process Scheduling Basics
The OS decides which process runs using algorithms like Round Robin or Priority Scheduling.
In cyber attacks, processes can abuse high priority to consume resources (DoS).

7. Linux Commands for Process Investigation

ps aux → List all processes.

top / htop → Monitor processes in real-time.

pidof <name> → Find process ID.

kill <PID> → Terminate a process.

lsof -p <PID> → View files used by a process.

strace -p <PID> → Trace system calls of a process.
