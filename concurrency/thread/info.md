1) What is a thread? <br>
    a) A thread is the smallest unit of processing that can be scheduled. <br>
    b) It's an instance of java.lang.Thread. There are two kinds of threads, platform threads and virtual threads. <br>
2) what is a platform thread? <br>
    a) A platform thread is implemented as a thin wrapper around an operating system (OS) thread. A platform thread runs Java code on its underlying OS thread, and the platform thread captures its OS thread for the platform thread's entire lifetime. Consequently, the number of available platform threads is limited to the number of OS threads. <br>
    b) Platform threads typically have a large thread stack and other resources that are maintained by the operating system. They are suitable for running all types of tasks but may be a limited resource. <br>

3) What is a virtual thread? <br>
    a) Like a platform thread, a virtual thread is also an instance of java.lang.Thread. However, a virtual thread isn't tied to a specific OS thread. A virtual thread still runs code on an OS thread. However, when code running in a virtual thread calls a blocking I/O operation, the Java runtime suspends the virtual thread until it can be resumed. The OS thread associated with the suspended virtual thread is now free to perform operations for other virtual threads. <br>
    b) Unlike platform threads, virtual threads typically have a shallow call stack, performing as few as a single HTTP client call or a single JDBC query.<br>
    c) Virtual threads are suitable for running tasks that spend most of the time blocked, often waiting for I/O operations to complete. However, they aren't intended for long-running CPU-intensive operations. <br>
    d) Virtual threads provide scale (higher throughput), not speed (lower latency). <br>
    e) When the Java runtime schedules a virtual thread, it assigns or mounts the virtual thread on a platform thread, then the operating system schedules that platform thread as usual. This platform thread is called a carrier. After running some code, the virtual thread can unmount from its carrier. This usually happens when the virtual thread performs a blocking I/O operation. After a virtual thread unmounts from its carrier, the carrier is free, which means that the Java runtime scheduler can mount a different virtual thread on it. <br>