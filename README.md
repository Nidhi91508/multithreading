# Experiment 3: Multithreading

**Subject:** Operating Systems (21CSC202J)  
**Experiment:** 3 — Multithreading

## Aim
To implement and study multithreading in C using the POSIX pthread library:
- **Part A:** Multiprocessor multithreading.
- **Part B:** Single-processor multithreading using CPU affinity and time-slicing.

## Files
- `experiment3_partA_multiprocessor.c` — creates four threads and waits for each thread to finish.
- `experiment3_partB_single_processor.c` — creates four threads and attempts to bind them to CPU core 0.
- `experiment3_multiprocessor_output.png` — output screenshot copied from the lab manual.
- `experiment3_single_processor_output.png` — output screenshot copied from the lab manual.

## Compile and run (Part A)
On Linux with GCC and pthread support:

```bash
gcc experiment3_partA_multiprocessor.c -o partA -pthread
./partA
```

## Compile and run (Part B)
The manual's Part B uses Linux-specific GNU CPU-affinity functions. Run it on a compatible Linux system:

```bash
gcc experiment3_partB_single_processor.c -o partB -pthread
./partB
```

## Expected behavior
- Part A prints one message for each of four threads. The order can vary between runs because thread scheduling is nondeterministic.
- Part B prints one time-slicing message for each of four threads. CPU affinity restricts the threads to CPU core 0 on supported Linux systems.

## Note
The two PNG files are the output screenshots from the supplied lab manual. Actual output ordering and process prompts can vary by system.
