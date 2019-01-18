# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Concurrency -- When two or more tasks shares resources in such a way that they seem to be running simultaneously (Virtual
   parallelism). 
   Parallelism -- Tasks that actually runs simultaneously
 
 ### Why have machines become increasingly multicore in the past decade?
 > In the beginning of the twenty first century the advancement in single core processor technology hit a roadblock due to the
   frequency-wall, ILP-wall, and the Power-wall. The solution to these challenges was to develop processors with multiple cores
   which when they are combined gives a better total performance than a single cored processor with the same surface area. Each of the
   cores in a multicore processor can run with a lower frequency, which makes the total power consumption smaller than the single cored
   processor with the same surface area.

 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > One of the biggest advantages to using concurrent programming is that it allows independent tasks to operate in such a manner
 that it seems like they are running simultaneously. A big advantage to this is that it in most cases will improve the utilization
 of the resources in the system.
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > It has both positive and negative sides. On the positive sides is that it concurrent programing gives a higher level of modularity
 and abstraction, which is great for a programs manageability. One of the most significant negative effects is that debugging in many
 cases will be more complex. Race conditions, deadlocks, and fair distribution of resources will also be a more challenging task in
 concurrent programming.

 ### What are the differences between processes, threads, green threads, and coroutines?
 > Process: Managed by OS. Has its own address space.
   Thread: Managed by OS. Same address space as the parent.
   Green thread: Same as thread, but not managed by OS.
   Coroutine: Not managed by OS. Function that has multiple entry/exit points, so that it can run more smothly 
 
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > pthread_create() -- creates a thread
   threading.Thread() -- creates a thread
   go (Go) -- uncertain, but something close to a green thread maybe?
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > In a CPU-bound multi-threaded program the GIL will make the program behave like a single-threaded program. It will actually
 have a longer execution time due to extra overhead caused by the threading.
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > You use multiple processes instead of threads. This is done through the multiprocessing module.
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > "GOMAXPROCS sets the maximum number of CPUs that can be executing simultaneously and returns the previous setting."
 https://golang.org/pkg/runtime/#GOMAXPROCS
