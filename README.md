# Multithreading-primenumbersMultithreading-primenumbers
Write a multithreaded program in C that outputs prime numbers. This program should work as follows: The user will run the program and will enter a number on the command line. The program will then create a separate thread that outputs all the prime numbers less than or equal to the number entered by the user. 

Code: 
3)
#include <pthread.h>
#include <stdio.h>
#include <stdlib.h>
void *prime(void *x);
int main() {
int x;	
scanf("%d",&x);
pthread_t tid; 
pthread_attr_t attr;
printf("Prime Numbers:\n");
pthread_attr_init(&attr);
pthread_create(&tid,&attr,prime,&x);
pthread_join(tid,NULL);
}
void *prime(void *x) {
  int i,j,end = *(int *)x;
for(i = 2; i < end; i++) {
int ans = 0;
for(j = 2; j < i; j++) {
         int result = i % j;
if(result == 0) {
ans = 1;
break;
}
}
if(ans == 0) {
printf("%d\n", i);
}
    }
 pthread_exit(0);
}

In terms of Operating system concept:-
In this programe i've got created multi thread.
This works as follow:

Step 1:- While running a program, user can enter a number on the statement.

Step 2:- Then the program create another thread which is become independent from the first one that output prime numbers but or adequate the given input by the user.
               
             In detail, unlike ‘java’, ‘c’ can’t support multi threading. Pthread are called posix threads are standard usage of thread with gcc compile. we are able to implement pthreads methodology selected: pthread.
              Pthread; the straightforward and reliable way of creating multithread applications. When a thread is formed using pthread but the initial thread, and new thread share same.
              The declaration of a variable in main() called thread-id, which is of type pthread-id. Which is an integer accustomed identify the thread within the system. After declaring thread-id, we call pthread –create() function to form a thread. pthread-create() takes 4 arguments,                                           	 In main() we declare a variable called thread_id, which is of type pthread_t, which is an integer accustomed identify the thread within the system. After declaring thread_id, we call pthread_create() function to form a thread.

pthread_create() takes 4 arguments.

The first argument might be a pointer to thread_id which is about by this function.
The second argument specifies attributes. If the value is NULL, then default attributes shall be used.                                                                                                                                                            The third argument is name of function to be executed for the thread to be created.
The fourth argument is utilized to pass arguments to the function, myThreadFun.
The pthread_join() function for threads is that the equivalent of wait() for processes. A call to pthread_join blocks the calling thread until the thread with identifier adequate the first argument terminates.
To compile a multithreaded program using gcc, we would like to link it with the pthreads library. On compilation we have got to input the amount which returns prime numbers
Additional Algorithm:-
#include <stdio.h>
#include <stdlib.h> 
#include <unistd.h>  //Header file for sleep(). man 3 sleep for details. 


#include <pthread.
void *myThreadFun(void *vargp) 
{ 
    sleep(1); 
    printf("Printing GeeksQuiz from Thread \n"); 
    return NULL; 
} 
int main() 
{
    pthread_t thread_id; 
    printf("Before Thread\n"); 
    pthread_create(&thread_id, NULL, myThreadFun, NULL); 
    pthread_join(thread_id, NULL); 
    printf("After Thread\n"); 
    exit(0);
}

This is a algorithm used in creation of pthread.

Complexity of the code:- N^2
