---
layout: post
title:  "Process Creation & Termination"
date:   2021-08-25 19:40:36 +0530
categories: OperatingSystem
---

### **Process Creation** <br/>

<br/>
	- **Parent** process create **child** processes, which, in turn create other processes, forming a tree of processes<br/>
	- Process identified and managed via a **process identifier** (pid)<br/>
	<br/>
	- Resource sharing options: <br/>
	<br/>
		1. Parent and children share all resources<br/>
		2. Children share subset of parent's resources <br/>
		3. Parent and child share no resources<br/>
		<br/>
	- Execution options: <br/>
	<br/>
		1. Parent and children execute concurrently <br/>
		2. Parent waits until children terminate <br/>
		<br/>
	- **Address Space: **<br/>
		1. Child duplicate of parent <br/>
		2. Child has a program loaded into it <br/>

### **Unix Examples** <br/>
<br/>
	- fork() system call creates new process<br/>
	- exec() system call used after a fork() to replace the process' memory space with a new program <br/>
	- Parent process calls wait() for the child to terminate <br/>

![Image Alt MemoryLayout](/assets/forkprocess.png) <br/>
<br/>

### **C Program Forking Seperate Process** <br/>

```javascript
	#include <sys/types.h>
	#include <stdio.h>
	#include <unistd.h>

	int main()
	{
		pid t pid;
			/* fork a child process */
			pid = fork();

			if (pid < 0) { /* error occurred*/
				fprintf(stderr, "Fork Failed");
				return 1;
			}
			else if (pid == 0) { /* Child Process */
				execlp("/bin/ls","ls",NULL);
			}
			else { /* Parent Process*/
			/* Parent will wait for the child to complete */
				wait(NULL);
				printf("Child Complete");
			}
			return 0;
	}

```
<br/>
### **Process Termination** <br/>
<br/>
- Process executes last statement and then asks the operating system to delete it using the exit() system call.<br/>
1. Returns status data from child to parent(via wait())<br/>
2. Process's resources are deallocated by operating system <br/>
<br/>
- Parent may terminate the execution of children processes using the abort() system call. Some reasons for doing so:<br/>
1. Child has exceeded allocated resources <br/>
2. Task assigned to child is no longer required <br/> 
3. The parent is exiting and the operating system does not allow a child to continue if its parent terminates <br/>
<br/>
- Some operating systems do not allow child to exists if its parent has termianted. If a process terminates, then all its children must also be terminated<br/>
- **Cascading termination**: All children, grandchildren, etc. are terminated<br/>
- The parent process may wait for termination of a child process by using the wait() system call. The call returns status information and the pid of the terminated process <br/>

```javascript
	pit t pid 
	int status 
	pid = wait(&status);
```
<br/>
### **ZOMBIE PROCESS**<br/> 
- If no parent waiting (did not invoke wait()) process <br/>
<br/>
### **ORPHAN PROCESS**<br/>
- If parent terminated without invoking wait, process is an orphan 



