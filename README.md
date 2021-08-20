# software-engineering-project
GPU applications are prone to concurrency bugs, which are notoriously difficult to reproduce and fix due to the sheer number of possible “instructions interleaving”. GPUs have also been shown to implement weak memory models, so that behaviors beyond those obtained from straightforward interleaving are possible, making GPU application debugging even more challenging.Test Benchmark metrics:
The GPU used for testing is a 2 GB GPU with max_iter limit of 1,000,000 for failing in single iteration, if done without any optimization.
1. Test Results without Fencing: 
1)Test serial number 2) Number of Iterations Before failing 3) Vector Size  4)Computed time complexity 5)Computed computing complexity
     1                        1                                 1000000         178 sec                      187 sec
     2                        1                                 1000000         178 sec                      181 sec
     3                        1                                 1000000         178 sec                      195 sec
2. Test Results with thread_fence:
1)Test serial number 2)Number of IterationsBefore failing 3)Vector Size 4)Computed time complexity 5)Computed computing complexity
          1                 15                              1000000            39 sec                                44.7 sec
          2                 15                              1000000            39 sec                                54.6 sec
          3                 15                              1000000            39 sec                                51.1 sec
Comparing the data from both the tables, we can see that the average time for 1 iteration in test without thread_fence is 187.67 sec. For test with thread_fence, the total average time for 15 iterations is 50.13 sec. For single iteration, it is 50.13/15 = 3.34 sec. From this we, can see that the optimized code is 187.67/3.34 = 56.188 or approximately 56 times faster than that without optimization.
Algorithm:
1. N = 0
Page 13
2. S -> List of processes with their kernel information
3. d = S[0]
4. x = length(list(process.kernel()))
5. for (N = 0, N < length(S), N++):
if d==0:
Multiply_Kernel<<>>() # Function to multiply kernel for exponentially increased
complexity
X++
Else if d!=0 and 21> N:
Addition_kernel<<>>() # Function for moderately increased complexity
X++
Else if d!=0 and N>=21:
Copy_Kernel<<>>() # Copying kernel information before deleting kernels
Reduction_kernel<<>>() # Deleting kernels for reducing complexity.



