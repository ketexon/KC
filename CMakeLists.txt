cmake_minimum_required(VERSION 3.25)

project(KC)

list(
    APPEND
    CMAKE_PREFIX_PATH
    "C:/Program Files/LLVM/lib/cmake/llvm"
    extern/catch2
)
find_package(LLVM CONFIG REQUIRED)
message(STATUS "Found LLVM ${LLVM_PACKAGE_VERSION}")
message(STATUS "Using LLVMConfig.cmake in: ${LLVM_DIR}")


include(CTest)

add_subdirectory(extern/catch2)
include(Catch)


add_subdirectory(KC)
add_subdirectory(Tests)