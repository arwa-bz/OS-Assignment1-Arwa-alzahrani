# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A process is a stand-alone program that runs independently and has its own address space, memory, and system resources. A thread, on the other hand, is a smaller unit of execution inside a process that shares resources and memory with other threads inside the same process. As a result, threads can be created more quickly and lightly than processes. While threads utilize pre-existing memory and resources, processes need additional overhead because the operating system must allocate new memory and resources. In order to effectively imitate concurrent execution without using unnecessary system resources, threads were employed in place of processes in this assignment.Additionally, unlike processes that need inter-process communication protocols, threads facilitate communication because they share the same memory area. Consequently, a more straightforward and effective method of imitating CPU scheduling behavior is to use threads.**


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:A process in Round-Robin scheduling is preempted and placed at the end of the ready queue if it does not complete its execution within the allotted time quantum. This avoids starvation and guarantees that each process receives an equal amount of CPU time. Until every other process has had a chance to run, the process will remain in the queue. It resumes execution for a different time quantum when its turn comes again. This cycle keeps going till the procedure is finished. The simulation output, where processes often enter and exit the CPU, makes this behavior quite evident. **

Example from my output:

P1 completed quantum 4000ms
Remaining time: 3980ms
P1 yields CPU for context switch
P1 added to ready queue 

**Explanation of example:In this instance, process P1 was running but did not complete in the allotted 4000 milliseconds. Consequently, it returned to the end of the ready queue and gave up the CPU. This enables P2 and P3, among other processes, to run before P1 is given another chance. This illustrates how Round-Robin scheduling guarantees process equity. Until there is no more time left, the process will keep going through the line. This behavior is consistent with the Round-Robin scheduling theory presented in operating system textbooks.**

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. **New**: P1 is in the New state when the thread object is created using new Thread(process) but before the start() method is called. At this point, the thread has been initialized but has not yet begun execution. This corresponds to the initial creation of the process in the simulation setup. The thread exists in memory but is not yet scheduled by the CPU. This stage is very brief but essential in the thread lifecycle.

2. **Runnable**: After calling the start() method, P1 enters the Runnable state, where it is ready to run but waiting for CPU allocation. In this simulation, the thread is placed in the ready queue along with other processes. The scheduler selects threads from this queue in FIFO order. While in this state, P1 is eligible for execution but not currently running. This reflects how operating systems manage multiple ready processes.

3. **Running**: P1 enters the Running state when the scheduler selects it and executes the run() method. During this state, the process actively uses the CPU and performs its assigned task. In the output, this is shown by messages like "P1 executing quantum". The process runs for a duration equal to the time quantum or its remaining time. This is the actual execution phase where progress is made.

4. **Waiting**:P1 enters the Waiting state when Thread.sleep() is called inside the run() method. This simulates the passage of execution time and temporarily pauses the thread. While sleeping, the thread does not use CPU resources and waits for the specified time to pass. This models real-world scenarios where processes may wait for I/O or timing events. After sleeping, the thread transitions back to Runnable.

5. **Terminated**: P1 reaches the Terminated state when its remaining time becomes zero and it completes execution. At this point, the thread finishes its run() method and cannot be restarted. In the output, this is indicated by messages like "finished execution". This marks the end of the thread lifecycle. The process is removed from scheduling permanently.

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Server Handling Requests

**Description**: 
Multiple client requests are handled concurrently by a web server, and each request may take some time to process. These requests require equitable CPU allocation and are frequently independent. It is the server's responsibility to make sure that no request blocks another. To effectively manage these concurrent processes, threads are frequently utilized. A thread can be used to represent each request.

**Why Round-Robin works well here**: 
By assigning a set time slice to each request, round-robin scheduling guarantees equity. This keeps the CPU from being monopolized by long-running queries. It makes the server more responsive, particularly when several people are using it at once. It also guarantees consistent performance across requests. It is therefore appropriate for settings where people share time, such as web servers.

### Example 2: Time-Sharing Operating Systems

**Description**: 
Many users and processes can operate simultaneously on modern operating systems. A user is able to run multiple apps at once. All processes must receive an equitable share of CPU time from the system. These executions are managed internally via threads. This gives the appearance of parallelism.

**Why Round-Robin works well here**: 
Round-Robin scheduling gives every process an equal chance to run. It guarantees that no process is starved of CPU time. The user experience and system responsiveness are enhanced as a result. It is particularly helpful in interactive systems that need to react quickly. Time slices are dependable in multitasking settings because they are predictable.
---

## Summary

**Key concepts I understood through these questions:**
1. How Round-Robin scheduling prevents famine and guarantees equity
2. The difference between threads and processes and their resource management
3. The lifecycle and states of a thread during execution

**Concepts I need to study more:**
1. Synchronization and deadlock handling
2. Advanced scheduling algorithms like Priority Scheduling
