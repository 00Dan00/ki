# Async
- Concurrency Model
- single CPU/thread. 
- Uses cooperative multitasking where tasks voluntarily yield control back to the event loop using `await`
- no overhead for context switching
- use cases: I/O Operations, 

# Multiprocessing
- creating multiple processes, each with its own python interpreter, memory space, ...
- those processes run in parallel (true parallelism)
- each process has its own memory space, means no shared data (only through IPC - Inter-process communication)
- has more overhead than multithreading (seperate memory space, IPC)
- use cases: CPU-bound tasks that require significant computational power and can be parallelized (data processing, scientific computations)

# Multithreading
- creates multiple Threads within the same process. 
- They share the same memory space and can run concurrently. (no true paralellism because of the GIL)
- Task switching requires less overhead than switching processes