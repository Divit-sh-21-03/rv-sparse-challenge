# rv-sparse-challenge

This is my implementation for the rv-sparse mentorship coding challenge. The goal was to implement sparse matrix-vector multiplication (SpMV) using the Compressed Sparse Row (CSR) format.

## How it works
The `sparse_multiply` function is broken into two main parts:
1. **CSR Construction:** It scans the input dense matrix to find non-zero elements and stores them into the provided `values`, `col_indices`, and `row_ptrs` buffers.
2. **SpMV Calculation:** It uses those CSR structures to calculate the result vector `y = A * x`.

**Constraint:** The implementation uses zero dynamic memory allocation (`malloc`, `calloc`, etc.) to keep it suitable for bare-metal or resource-constrained environments. [cite_start]All memory is pre-allocated by the caller. [cite: 110, 118]

## Project Structure
* `challenge.c`: Contains the core implementation and the test harness.
* `test_results.png`: Screenshot showing the test harness passing 100/100 iterations.

## Building and Running
To compile and run the test on Windows (via GCC/MinGW) or Linux:

```bash
gcc -lm -o run challenge.c
./run
