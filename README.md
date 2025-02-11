# Off-by-One Error in C++ Vector Iteration

This repository demonstrates a common off-by-one error that can occur when iterating over vectors (or other dynamic arrays) in C++.  The error arises from incorrectly handling the loop termination condition, causing an attempt to access an element beyond the valid range of the vector.

The file `bug.cpp` contains the buggy code, while `bugSolution.cpp` provides the corrected version.

## How to reproduce
1. Clone this repository.
2. Compile and run `bug.cpp` (you'll likely get a segmentation fault or similar error).
3. Compile and run `bugSolution.cpp` (this will correctly print the vector elements).

## Understanding the Error
The original code attempts to access `vec[vec.size()]`, which is outside the bounds of the vector (valid indices are 0 to `vec.size()-1`). This leads to undefined behavior, often resulting in a program crash.

## Solution
The corrected code in `bugSolution.cpp` uses the condition `i < vec.size()`, ensuring that the loop terminates before attempting to access an invalid element.