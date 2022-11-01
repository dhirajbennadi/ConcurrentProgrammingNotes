# OpenMP (Open Multiprocessing)

1. Focuses on prallelizing essential parts of sequential programs - a design goal of OpenMP is to optionally parallelize a sequential program
2. Cross platfor/language (C,C++, Fortran)
3. Fork join parallelism with explicit master thread

# Basic Structure
```
#include <omp.h>
int main()
{
    //Serial Code

    #pragma omp parallel
    {
        // Parallel region executed by all threads

    }

    //Serial code
}
```

# Runtime Functions
Setting/Querying Program State: `int omp_get_num_threads(void)`

# Memory model is disturbed in OpenMP

# Work Sharing Constructs are used within an OpenMP parallel region

# Loop Scheduling
1. Static - Assign threads to work on iterations. This is slower as a thread might take more time to process
2. Dynamic - Available thread is executed - Queue is used
3. Guided

# Sections
Each section executes in parallel by a different thread
-> Implied barrier at the end

`nowait` -> Preventing data races

