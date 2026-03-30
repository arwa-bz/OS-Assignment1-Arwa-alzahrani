# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [March 28, 2026, 3:00 PM]
**What I did**: Set up the project and updated my student ID
**Details**: 
- Created GitHub account with my university email
- Located the file SchedulerSimulation.java
- Updated my student ID to 445052160
- Compiled and ran the program successfully

**Challenges**: It was first difficult to understand the code's structure and the creation and scheduling of processes.

**Solution**: Read the code carefully, paying close attention to each stage of the execution sequence.

**Time spent**: 2 hours

---

## Your Development Log:

### Entry 2 - [March 28, 2026, 6:30 PM]
**What I did**: Analyzed Round-Robin scheduling logic

**Details**: 
- watched as processes entered and exited the queue.
- determined the application of time quantum to each process.
- observed that incomplete processes are re-added.
- concentrated on the management of the ready queue
  
**Challenges**: It was difficult to fully understand how context switching works in practice

**Solution**: Ran the program multiple times and compared outputs to see patterns

**Time spent**: 3 hours

---

### Entry 3 - [March 29, 2026, 7:00 PM]
**What I did**: Implemented Feature 1 (Process priority + display)

**Details**: 
-Added priority attribute to each process
- Modified the output to display process priority
- Confirmed that every process in the ready queue displays the appropriate priority.

**Challenges**: Making sure the priority value is accurately displayed and stored without interfering with the current logic

**Solution**: After every little modification, the application was tested, and formatting problems were resolved.

**Time spent**: 4 hours

---

### Entry 4 - [March 30, 2026, 2:00 PM]
**What I did**: Implemented Feature 2 (Context switch counter)

**Details**: 
- Added a counter to track number of context switches
- Updated logic to increment counter every time CPU switches processes
- Displayed total context switches at the end (e.g., 35 switches)
  
**Challenges**: Figuring out exactly where to increment the counter without counting incorrectly

**Solution**: Placed the counter update after each quantum completion when a process yields CPU

**Time spent**: 2 hours

---

### Entry 5 - [March 30, 2026, 5:00 PM]
**What I did**: Implemented Feature 3 (Waiting time + summary table)

**Details**: 
- Calculated waiting time for each process
- Stored waiting time values
- made a summary table that displays the waiting time, burst time, and process name.
- Results were confirmed using program output.

**Challenges**: Knowing how to accurately compute waiting times over several cycles

**Solution**:closely monitored execution and waiting times, and output logs were used for validation. 

**Time spent**: 4 hours

---

### Entry 6 - [March 30, 2026, 10:00 PM]
**What I did**: Final testing and output verification

**Details**: 
- Ran the full simulation multiple times
- confirmed Round-Robin scheduling's proper operation
- Verified process completion and ready queue transitions
- Verified that every functionality is operating properly

**Challenges**: Ensuring consistency in output and avoiding duplicate or incorrect entries

**Solution**: Carefully reviewed logs and adjusted minor issues in display

**Time spent**: 2 hours

---

### Entry 7 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [3 days]

**Most challenging part**: figuring out how processes transition between states and accurately computing waiting times over several scheduling cycles.

**Most interesting learning**: Observing how Round-Robin scheduling guarantees process equity and avoids famine

**What I would do differently next time**: I would plan the implementation steps earlier and test each feature more incrementally to reduce debugging time
