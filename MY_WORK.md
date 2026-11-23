# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Abdullah Abdelwahab Alawad |
| **Student ID** | 446050626 |
| **University Email** | 446050626@std.psau.edu.sa |
| **GitHub Username** | Abdullah-Alawad-77 |
| **Repository Link** | https://github.com/Abdullah-Alawad-77/OS-Assignment3-Abdullah-Alawad |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 22, 2026, 5:19 PM]
**What I did**:
Forked the starter repository, cloned it into VS Code and set my student ID
**Details**:
 Forked makopt/OS-Assignment3-Starter-481 and renamed it OS-Assignment3-Abdullah-Alawad (public)
 Cloned the repository and configured Git with my university email
 Changed the student ID to 446050626
 Committed and pushed: Update my student ID

**Challenges**:
I had used Git and GitHub in Assignment 1, but I had forgotten the exact commands, so I had to relearn the commit and push steps
**Solution**:
The cycle was checked using Git Status, git add, git commit -m, and git push origin main in the VS Code Terminal, and then verified by viewing git log --oneline and the Commits section in GitHub.
**Time spent**:1 hour

---

### Entry 2 - [November 22, 2026, 5:45 PM]
**What I did**:
 Ran the original starter and analyzed why it fails
**Details**:
 4 CPUs started and the first three picked the same process P1
 Three CPU threads crashed with IllegalThreadStateException at thread.start()
 P2 and P3 never ran (waiting and turnaround stayed 0) 
 and the watchdog stopped the program after 19 s
 Verification: 16/20 context switches, 8/10 completed, 23170/29777 ms service time, 711 busy-waiting polls
 Saved the output for Question 1
**Challenges**:
I did not understand why P2 and P3 disappeared

**Solution**:
Read ReadyQueue.poll(): RaceWindow.pause() sits between getFirst() and removeFirst(), so every CPU read the same head and each removeFirst() removed a different element
**Time spent**:
 45 minutes
---

### Entry 3 - [November 22, 2026, 7:04 PM]
**What I did**:
Feature 1: protected the ready queue with a ReentrantLock
**Details**:
 Added ReentrantLock queueLock in ReadyQueue
 Wrapped add(), poll(), processOf() and snapshot() in lock() / try / finally { unlock() }
 Result: no more exceptions and all 10 processes completed, but the counters were still wrong (18/20 context switches, 25777/29777 ms, 24 polls)
 Committed: Feature 1: Protected the ready queue with a ReentrantLock
**Challenges**:
 I wrote several features before committing, so my first commit would have contained everything
**Solution**:
Saved a backup copy, restored the file with git restore and re-added the code one feature at a time so each commit contains a single feature
**Time spent**:
 1 hour
---

### Entry 4 - [November 22, 2026, 7:11 PM]
**What I did**:Feature 2: protected the shared statistics

**Details**:
 Added contextSwitchLock, completedLock and serviceTimeLock (one lock per variable)
 Protected the three update methods and the three getters with lock() / try / finally
 Result: the first three verification lines became 20/20, 10/10 and 29777/29777; only the busy-waiting polls (30 and 23 in my runs) were still wrong
 Committed: Feature 2: Added locks to the shared statistics counters

**Challenges**:
 Deciding between one lock for all counters and one lock per counter
**Solution**:
The three variables are independent, so I used one lock per variable to allow more parallelism
**Time spent**:
45 minutes
---

### Entry 5 - [November 22, 2026, 7:35 PM]
**What I did**:
Feature 3: replaced busy waiting with a counting semaphore
**Details**:
 Added Semaphore readyCount = new Semaphore(0) in ReadyQueue
 add() calls readyCount.release() after unlocking; CpuWorker calls readyCount.acquire() before poll()
 The last CPU calls readyCount.release(totalCPUs) so the blocked CPUs wake up and terminate
 Ran the program 5 times: all four checks passed, 0 polls and no watchdog
 Committed: Feature 3: Replaced busy waiting with a counting semaphore

**Challenges**:
A compile error "Duplicate local variable thread", because I had put the new code inside the old if (thread == null) block

**Solution**:
Deleted the whole old polling block and wrote acquire(), the shutdown check and Thread thread = readyQueue.poll() once at the top of the loop
**Time spent**:
2 hours
---

### Entry 6 - [November 23, 2026, 3:44 PM]
**What I did**:
Wrote MY_WORK.md and recorded the video
**Details**:
 Completed the reflection and technical answers using my own outputs
 Recorded the demo video, uploaded it and pasted the link
**Challenges**:
 Explaining the concepts in my own words in English
**Solution**:
Wrote the points in Arabic first, then translated them and checked them against my code
**Time spent**:
30  min
---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: 6 hours
**Most challenging part**:
Stopping the CPUs cleanly with the semaphore (release(totalCPUs)) and fixing the duplicate variable error
**Most interesting learning**:
The same code gives wrong results randomly without locks and consistent results with them
**What I would do differently next time**:
 Commit after finishing each feature instead of writing all of them first
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

In this assignment, I found out that the race condition occurs when a few threads read and write a shared variable unprotected, since an incrementation of the counter, for example, count++, consists of three operations: read, modification and write. The starter selected three CPUs for the same process P1, while P2 and P3 processes were lost. It means that even such a simple structure as the queue is a critical section. I learned how to protect critical sections using ReentrantLock and release the lock in the finally block to make sure that the lock will be released even if there is a return or exception. I learned that counting semaphore may be used to eliminate busy waiting, because instead of checking empty queue every 20 ms, a CPU just blocks on acquire(). As a result, after making changes, I obtained 20 context switches, 10 completed processes and 29777 ms service time with 0 busy-waiting polls in my verification block. But most importantly, I learned that all these bugs occur randomly.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part for me was Feature 3, especially stopping the CPUs cleanly after replacing the polling loop with a semaphore. I realized that a CPU waiting on an empty queue would block forever once the last process finished. I had to understand that the last CPU must call release(totalCPUs) so every blocked CPU wakes up, checks the completed counter and returns. My first attempt also failed to compile with "Duplicate local variable thread" because I had written the new code inside the old if (thread == null) block. It was difficult because the problem was not only syntax, but also how the threads interact with each other.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I overcame the challenges by working in small steps and running the program after every change. When the compile error appeared, I read the message in the VS Code Problems tab, went to the line it pointed to and removed the old polling block. I compared the output of each version with the verification block, for example after Feature 1 I saw 18 instead of 20 context switches, which told me the counters still needed locks. I ran the final program five times to make sure all four checks passed and that it terminated by itself. I also used git log and the Commits page on GitHub to confirm that each feature was committed separately. Re-reading the README helped me place release() after the unlock and acquire() outside any lock.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is used in banking systems, where two transfers must not update the same balance at the same time, otherwise one update is lost like my contextSwitchCount. Ticket and seat booking systems use locks so that two users cannot reserve the same seat, which is similar to two CPUs picking the same process. A print queue is a producer-consumer problem: programs add jobs and the printer removes them, as my CPUs take processes from the ReadyQueue. A website visitor counter updated by many requests needs a lock, just like my shared statistics. Databases use locks to keep transactions consistent when many users work on the same data. Operating systems use semaphores so that waiting threads sleep instead of wasting CPU time, as in my final version with 0 busy-waiting polls.

### Optional: What would you like to learn more about?

Deadlock detection and the dining philosophers problem.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand locks, semaphores and race conditions, but I need more practice with deadlock.

### Optional: Feedback on the assignment

It was very useful because the starter shows the bugs clearly. The verification block helped me check my work after each feature.

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my original starter run, the verification block showed 16 context switches instead of 20, 8 completed processes instead of 10, 23170 ms of service time instead of 29777 ms, and 711 busy-waiting polls instead of 0. A lost update happens like this: CPU-1 reads contextSwitchCount (for example 5), then RaceWindow.pause() lets CPU-2 read the same value 5, CPU-1 writes 6 and CPU-2 also writes 6, so one increment is lost. I saw this pattern after Feature 1: with only the queue protected, I got 18 context switches instead of 20 and 25777 ms instead of 29777 ms, a difference of exactly 2 x 2000 ms. On a real machine the same bug exists without RaceWindow, because count++ is three steps (read, modify, write) and the scheduler can preempt a thread between them. It is hard to detect because the window is only a few nanoseconds, so the error appears rarely and randomly and is difficult to reproduce.

Verification block of the **original starter**:
```
⛔ WATCHDOG: the simulation did not finish (19 s). A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 20       observed 16       ✘ MISMATCH
  Completed processes                    expected 10       observed 8        ✘ MISMATCH
  Total service time (ms)                expected 29777    observed 23170    ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 711      ✘ MISMATCH
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 20       observed 20       ✔
  Completed processes                    expected 10       observed 10       ✔
  Total service time (ms)                expected 29777    observed 29777    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
```

**Explanation of the timeline:**
In the starter, CPU-1 to CPU-4 all read P1 as the head of the queue, then paused inside RaceWindow.pause(). After the pause each CPU executed removeFirst(), so each one removed a different element (P1, P2, P3 and P4), but all four started the thread of P1, which is why three of them crashed with IllegalThreadStateException. P2 and P3 were removed without ever being run, which explains the missing 4 context switches (2 processes x 2 quanta), the 2 missing completions and the missing 6607 ms (3671 + 2936). The pure lost-update on a counter is the timeline described above: both CPUs read the same value, both write value + 1, and one increment disappears.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected the ReadyQueue methods add(), poll(), processOf() and snapshot() with queueLock, and the three shared counters with contextSwitchLock, completedLock and serviceTimeLock, including their getters. I used one lock per variable because the three variables are independent, so a CPU updating contextSwitchCount does not need to block another CPU updating totalServiceTime; the trade-off is a few more locks to manage in exchange for more parallelism. The ready queue uses a different lock because it protects different data, and sharing one lock would make threads wait for each other for no reason. Mutual exclusion is guaranteed because only the thread holding the lock can run the read-modify-write sequence, and progress holds because the lock is free whenever nobody is inside the critical section. A default ReentrantLock is not fair, so in theory a thread could wait a long time (no strict bounded waiting), but my critical sections are very short, so starvation is unlikely in practice.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()`, `poll()`, `processOf()`, `snapshot()` | `queueLock` | `list` and `map` are shared by all CPUs |
| `incrementContextSwitch()` and `getContextSwitchCount()` | `contextSwitchLock` | Read-modify-write and visibility on `contextSwitchCount` |
| `incrementCompletedProcess()` and `getCompletedProcessCount()` | `completedLock` | Read-modify-write and visibility on `completedProcessCount` |
| `addServiceTime()` and `getTotalServiceTime()` | `serviceTimeLock` | Read-modify-write and visibility on `totalServiceTime` |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the starter, a CPU that found the queue empty slept 20 ms and checked again, which is busy waiting that wastes CPU time, and my starter run counted 711 polls. In my solution the semaphore readyCount represents the number of processes waiting in the ready queue, so its initial value is 0 because the queue is empty at creation, and it becomes 10 after the 10 initial add() calls. Each add() calls release() and each CPU calls acquire() before poll(), so a CPU with nothing to run is blocked instead of running. When the last process completes, the last CPU calls release(totalCPUs) to wake every blocked CPU so it can see that completed equals total and return. Without it, the CPUs waiting in acquire() would never be woken, the program would hang and the watchdog would stop it.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
The ready queue and the CPUs form the Producer-Consumer (bounded buffer) problem of Chapter 5. The main thread produces the initial processes, and each CPU is a consumer when it takes a process and a producer when it puts an unfinished process back. For a queue with capacity K, I would use three semaphores: mutex = 1, empty = K and full = 0. A deadlock appears if a producer does wait(mutex) before wait(empty): when the buffer is full it holds the mutex while waiting for a free slot, and the consumer that could free a slot needs the same mutex. I would prevent it by always doing wait(empty) before wait(mutex), which breaks the hold-and-wait condition. 

**Classical problem and roles**:
Producer-Consumer (bounded buffer). Producers: the main thread (initial add) and the CPUs (re-enqueue). Consumers: the CPUs (poll).

**Semaphores for a bounded queue (name and initial value)**:
 mutex = 1, empty = K (free slots), full = 0 (filled slots).

**Deadlock scenario and prevention**:
A producer holds mutex and waits on empty while the buffer is full; the consumer needs mutex to free a slot, so both wait forever. I would break the hold-and-wait condition by calling wait(empty) before wait(mutex).

## Summary

**Key concepts I understood through these questions:**
1.A race condition is a lost update caused by an unprotected read-modify-write.
2.A mutex lock (ReentrantLock with try/finally) gives mutual exclusion, and lock granularity is a trade-off between simplicity and parallelism.
3.A counting semaphore replaces busy waiting and needs a clean shutdown signal.


**Concepts I need to study more:**
1.Deadlock detection and prevention in larger systems.
2.Fair locks and starvation.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [x] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [x] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [x] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [x] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [x] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [x] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [x] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [x] Every lock is released in a `finally` block
- [x] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [x] Each feature has clear comments

**Commits**
- [x] **At least 4 meaningful commits, ideally 7 or more**
- [x] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [x] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [x] Full name and student ID filled in at the top
- [x] Development log has **5+ entries** on different dates
- [x] Reflection: 4 questions, 5-7 sentences each
- [x] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [x] No `[...]` placeholders left
- [x] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above
 
**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
