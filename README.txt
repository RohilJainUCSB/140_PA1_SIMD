With only -O optimization:
    Naive sum:  Time:  7944.0000 microseconds.      GFLOPS:  1.26
    SSE-128:    Time:  5617.0000 microseconds.      GFLOPS:  1.78
    AVX-256:    Time:  4253.0000 microseconds.      GFLOPS:  2.35
With -O3 optimization:
    Naive sum:  Time:  4075.3333 microseconds.      GFLOPS:  2.45
    SSE-128:    Time:  5092.3333 microseconds.      GFLOPS:  1.96
    AVX-256:    Time:  4156.0000 microseconds.      GFLOPS:  2.41

For -O compilation flag, is the naïve sum substantially slower than others?
Naive sum is substantially slower that others. This is because the minimal optimization with a very
naive implementation means the process running the program has to handle the entire set of operations.
This means the program time would not be optimized with parallelization so it would come at a high
time cost.

For -O3 compilation flag, is the naïve sum is substantially slower than others?
It is not. The -O3 optimization parallelization significantly speeds up the processeing of the sum
by running summations in a more ideal manner in parallel as opposed to sequentially. We see that the
time for the -O3 optimization is quite similar to the AVX-256 optimization, so it is very possible
that the compiler optimized the run pattern to that one.