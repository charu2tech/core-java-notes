1) <b> Task scheduling framework: <b> Executor is a task scheduling framework.
   eg: Executors::newSingleThreadExecutor, Executors::newFixedThreadPool
   The built-in implementations offer configurable policies such as queue length limits and saturation policy (see RejectedExecutionHandler) that can improve the stability of applications by preventing runaway resource use. <br>

2) <b> Fork/join framework <b>: Based on the ForkJoinPool class, this framework is an implementation of Executor. It is designed to efficiently run a large number of tasks using a pool of worker threads. A work-stealing technique is used to keep all the worker threads busy, to take full advantage of multiple processors. <br>

3) Concurrent Collections, Synchronizers(cooridnate between threads like semaphore, cyclicbarrier, countdownlatch, phaser, exchanger etc), Atomic Variables, thread local variables, Locks, virtual threads. <br>

4) Nano second granularity timing:  The System.nanoTime method enables access to a nanosecond-granularity time source for making relative time measurements and methods that accept timeouts. <br>


lock, race condition, inconsistencies in the data strucutre, bugs, crashes, unexpected behavior,thread pools and blocking queues, a framework fo vr asynchronous execution of tasks, synchronization utilities such as counting semaphores; atomicariables; locks; and condition variables, deadlock, starvation, race conditions, or excessive context switch