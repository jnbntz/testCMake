# Testing CMake with CUDA

A simple CUDA example that demonstrates vector addition on the GPU using CMake as the build system.

## Project Structure

```
.
├── CMakeLists.txt
└── src/
    └── vector_add.cu
```

## Prerequisites

- CMake (version 3.18 or higher)
- CUDA Toolkit
- A CUDA-capable GPU
- C++ compiler compatible with your CUDA version

## Building the Project

1. Create a build directory:
```bash
mkdir build
cd build
```

2. Configure the project with CMake:
```bash
cmake ..
```

Note: By default, the project is configured for CUDA architecture 75 (RTX 20xx series). If you have a different GPU, you may need to modify the `CMAKE_CUDA_ARCHITECTURES` in CMakeLists.txt. Common values are:
- 60 for Pascal (GTX 10xx)
- 70 for Volta
- 75 for Turing (RTX 20xx)
- 86 for Ampere (RTX 30xx)
- 89 for Ada Lovelace (RTX 40xx)

3. Build the project:
```bash
cmake --build .
```

## Running the Program

After building, you can run the vector addition example:

```bash
./vector_add
```

The program will:
1. Create two random vectors
2. Perform vector addition on the GPU
3. Verify the results
4. Print "Test PASSED" if successful

## Expected Output

If everything works correctly, you should see output similar to:
```
[Vector addition of 50000 elements]
CUDA kernel launch with 196 blocks of 256 threads
Test PASSED
Done
```
