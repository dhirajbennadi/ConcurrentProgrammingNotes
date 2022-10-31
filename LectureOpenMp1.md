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