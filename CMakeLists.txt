cmake_minimum_required(VERSION 3.18)
project(cuda_example CUDA CXX)

# Set CUDA architectures if not already set
if(NOT DEFINED CMAKE_CUDA_ARCHITECTURES)
    set(CMAKE_CUDA_ARCHITECTURES 75)
endif()

# Enable C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CUDA_STANDARD 11)
set(CMAKE_CUDA_STANDARD_REQUIRED ON)

# Add executable
add_executable(vector_add src/vector_add.cu) 