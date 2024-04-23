# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

Developed by : AMIRTHAVARSHINI V

Register Number : 212223040014

## C Program to print process ID and parent Process ID using Linux API system calls
~~~
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
~~~

## OUTPUT
![323363651-277a5ef9-b0c2-4e5b-ad59-4a415db2c31c](https://github.com/amirthaviswanathan05/Linux-Process-API-fork-wait-exec/assets/149035397/bc2e3178-0156-45bd-8b36-a8b2318c9320)


## C Program to create new process using Linux API system calls fork() and exit()
~~~
#include <stdio.h>
#include<stdlib.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
~~~

## OUTPUT
![323363997-88cf0f5e-c8fc-4341-b71a-c87c6979fdf1](https://github.com/amirthaviswanathan05/Linux-Process-API-fork-wait-exec/assets/149035397/a623f96a-c61f-409e-9669-e0872bada889)



## C Program to execute Linux system commands using Linux API system calls exec() family
~~~
#include <unistd.h>
#include <stdio.h>
#include <stdlib.h>
int main()
{
	printf("Running ps with execlp\n");
	execlp("ps", "ps", "ax", NULL);
	printf("Done.\n");
	exit(0);
}
~~~

## OUTPUT

![323364224-1842c773-69d6-4a4d-9e90-fd5f92813952](https://github.com/amirthaviswanathan05/Linux-Process-API-fork-wait-exec/assets/149035397/4f0d2cfd-3765-48cd-a003-c10216e3a113)


# RESULT:
The programs are executed successfully.
