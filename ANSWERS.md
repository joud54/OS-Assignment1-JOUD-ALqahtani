# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A thread is a smaller unit of execution within the same process that shares memory, whereas a process is an active program with its own memory space and system resources.  
Because they need independent memory allocation, processes are heavier and take longer to create, whereas threads are faster and lighter.  
Since all processes are mimicked within the same program, sharing memory facilitates execution, which is why we employed threads in this assignment.  

Additionally, threads make it possible to more effectively emulate CPU scheduling without having to write several separate programs.  
As a result, the simulation is quicker and simpler to run.**

[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:In Round-Robin scheduling, if a process does not finish within its assigned time quantum, it is moved to the end of the ready queue.  
This ensures fairness, as every process gets an equal chance to use the CPU.  
The process will wait until all other processes in the queue get their turn, then it will execute again.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
↻ P1 yields CPU for context switch
➕ P1 (Priority: 2) added to ready queue │ Burst time: 8665ms
```

**Explanation of example:**
In this instance, process P1 did not complete its entire burst time despite running for 4000 ms.  
It gave up the CPU because it has 4665 ms left.  
It was then moved to the end of the ready queue so that other operations could continue.  
When P1 reaches the front of the queue once more later in the output, it has another opportunity to execute.  
This illustrates how Round-Robin scheduling keeps all processes equitable.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. **New**:  
P1 is in the New state when it is first created at the beginning of the program before being added to the ready queue.

2. **Runnable**:  
P1 enters the Runnable state when it is added to the ready queue as shown in the output:

➕ P1 (Priority: 2) added to ready queue │ Burst time: 8665ms

At this point, it is ready to be executed by the scheduler.

3. **Running**:  
P1 becomes Running when it is selected by the scheduler and starts executing:

▶ P1 executing quantum [4000ms]


4. **Waiting**:  
P1 enters the Waiting state when it finishes its quantum but still has remaining time:

↻ P1 yields CPU for context switch

It waits in the ready queue until it gets another turn.

5. **Terminated**:  
P1 reaches the Terminated state when it completes all its execution:

✓ P1 finished execution!

At this point, its remaining time becomes zero and it exits the system.
---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Server

**Description**: 
A web server manages several client requests concurrently.

**Why Round-Robin works well here**: 
Every request receives an equal amount of CPU time thanks to Round-Robin.  
It stops one request from preventing other requests.  
This enhances fairness and responsiveness.

### Example 2: Operating System Task Scheduling 

**Description**: Operating systems can run several programs at once.

**Why Round-Robin works well here**: 
It guarantees that every application receives the same amount of CPU time.  
This enhances user experience and keeps the system from freezing.  
Additionally, it offers consistent performance.
---

## Summary

**Key concepts I understood through these questions:**
1. The distinction between processes and threads  
2. The behavior of round robin scheduling  
3. The lifespan of a thread

**Concepts I need to study more:**
1. Coordinating  
2. Sophisticated algorithms for scheduling
