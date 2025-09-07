# 🌟 CPU Scheduling Notes

## 📚 Contents / Questions Covered
1. What is CPU Scheduling?  
2. Why do we need CPU Scheduling?  
3. When does CPU Scheduling happen?  
4. Types of CPU Scheduling  
5. CPU Scheduling Algorithms Overview  
6. First Come First Serve (FCFS) Scheduling  
7. Shortest Job First (SJF) Scheduling  
8. Priority Scheduling  
9. Round Robin (RR) Scheduling  

---

## 1. What is CPU Scheduling?  
In an Operating System (OS), many processes often wait to use the CPU.  
The **CPU scheduler** decides which process will run next when multiple processes are ready.  

> This decision affects system performance, including speed, waiting time, and fairness.

---

## 2. Why do we need CPU Scheduling?  
CPU is the most important resource in a system. Without proper scheduling:  
- Some processes may wait forever.  
- CPU may stay idle while processes are waiting.  
- System performance becomes slow and unfair.  

**Benefits of CPU Scheduling:**  
✅ Keep CPU busy  
✅ Reduce waiting time  
✅ Ensure fair allocation to all processes  
✅ Improve response time for users  

---

## 3. When does CPU Scheduling happen? ❗  
CPU scheduling occurs whenever the CPU becomes free. This can happen in situations like:  
- A process switches from **running → waiting** (e.g., I/O request).  
- A process **terminates**.  
- A process is **interrupted** (e.g., in Round Robin scheduling).  

---

## 4. Types of CPU Scheduling

### 4.1 Preemptive Scheduling
- OS can **stop a running process** and allocate CPU to another process.  
- Examples: Round Robin, Preemptive Priority, Shortest Remaining Time First (SRTF)  
- Useful in **real-time systems** and multitasking.

### 4.2 Non-Preemptive Scheduling
- Once a process starts, it **cannot be stopped** until it finishes or waits for I/O.  
- Examples: FCFS, Non-preemptive SJF, Non-preemptive Priority  
- Simpler but **less responsive**.

---

## 5. CPU Scheduling Algorithms Overview
1. **FCFS (First Come First Serve):** Simplest, like a queue.  
2. **SJF (Shortest Job First):** Prefers shorter processes to reduce waiting time.  
3. **Priority Scheduling:** CPU given based on process priority.  
4. **Round Robin (RR):** Fair sharing with fixed time slices.

---

## 6. First Come First Serve (FCFS)

- Processes are executed in the **order of arrival**.  
- **Non-preemptive:** Once a process starts, it runs till completion.  

**Example:**

| Process | Arrival Time (AT) | Burst Time (BT) |
|---------|------------------|----------------|
| P1      | 0                | 5              |
| P2      | 1                | 3              |
| P3      | 2                | 8              |

**Gantt Chart:**  
| P1 | P2 | P3 |
0 5 8 16


**Completion Times (CT):** P1=5, P2=8, P3=16  
**Turnaround Time (TAT = CT - AT):** P1=5, P2=7, P3=14  
**Waiting Time (WT = TAT - BT):** P1=0, P2=4, P3=6  

**Final Table:**

| Process | AT | BT | CT | TAT | WT |
|---------|----|----|----|-----|----|
| P1      | 0  | 5  | 5  | 5   | 0  |
| P2      | 1  | 3  | 8  | 7   | 4  |
| P3      | 2  | 8  | 16 | 14  | 6  |

✅ **Average TAT = 8.67, Average WT = 3.33**

---

## 7. Shortest Job First (SJF) Scheduling

- Process with **smallest burst time** runs first.  
- Goal: Minimize waiting time.  
- Types:  
  - **Non-preemptive SJF:** Process runs till completion.  
  - **Preemptive SJF (SRTF):** A new shorter process can interrupt the current one.

**Example (Non-preemptive):**

| Process | AT | BT |
|---------|----|----|
| P1      | 0  | 7  |
| P2      | 2  | 4  |
| P3      | 4  | 1  |
| P4      | 5  | 4  |

**Gantt Chart:**  
| P1 | P3 | P2 | P4 |
0 7 8 12 16


**Final Table:**

| Process | AT | BT | CT | TAT | WT |
|---------|----|----|----|-----|----|
| P1      | 0  | 7  | 7  | 7   | 0  |
| P2      | 2  | 4  | 12 | 10  | 6  |
| P3      | 4  | 1  | 8  | 4   | 3  |
| P4      | 5  | 4  | 16 | 11  | 7  |

✅ **Average TAT = 8, Average WT = 4**  

---

## 8. Priority Scheduling

- Each process has a **priority number**; smaller number → higher priority.  
- CPU goes to **highest priority process** first.  
- Tie → use **FCFS**.  
- Types: Non-preemptive and Preemptive.  
- **Problem:** Starvation of low-priority processes.  
- **Solution:** Aging → gradually increase waiting processes’ priority.

**Example (Non-preemptive):**

| Process | AT | BT | Priority |
|---------|----|----|---------|
| P1      | 0  | 5  | 2       |
| P2      | 1  | 3  | 1       |
| P3      | 2  | 8  | 4       |
| P4      | 3  | 6  | 3       |

**Gantt Chart:**  
| P1 | P2 | P4 | P3 |
0 5 8 14 22


---

## 9. Round Robin (RR) Scheduling

- **Fair sharing** CPU scheduling algorithm.  
- Every process gets a **fixed time quantum**.  
- If not finished, process goes to the **back of the queue**.

**Steps:**  
1. Ready processes in a **circular queue**.  
2. Each process runs for **time quantum** or until completion.  
3. If not done → goes to end of queue.  
4. Repeat until all processes complete.

**Key Points:**  
- Preemptive  
- Good for **time-sharing systems**  
- **Time quantum** affects performance:  
  - Too small → overhead from context switching  
  - Too large → behaves like FCFS  

**Example (High-level):**

| Process | BT |
|---------|----|
| P1      | 10 |
| P2      | 4  |
| P3      | 6  |

**Time Quantum = 3**  
**Execution order:**  
P1 → P2 → P3 → P1 → P3 → P1 → P2 → P3 → P1  

License

This content is open-source and free to use under the MIT License.

Author:

Created by Yamuna Gandalla – a beginner in cybersecurity with a mission to learn and share.





