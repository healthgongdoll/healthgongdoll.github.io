---
layout: post
title:  "Process Creation & Termination"
date:   2021-08-25 19:40:36 +0530
categories: OperatingSystem
---

### **Process Creation** <br/>
d
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


