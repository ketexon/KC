set(INCLUDE include/KC)
set(SRC src)

add_library(
    KC
    STATIC
    ${INCLUDE}/KC.hpp
    ${SRC}/KC.cpp
)

target_include_directories(
    KC
    PUBLIC
    include
)

set_target_properties(
    KC
    PROPERTIES CXX_STANDARD 20
)

# LLVM
target_include_directories(
    KC
    PUBLIC
    ${LLVM_INCLUDE_DIRS}
)

message("LLVM Include Dirs: ${LLVM_INCLUDE_DIRS}")

target_compile_definitions(
    KC
    PRIVATE
    ${LLVM_DEFINITIONS}
)

llvm_map_components_to_libnames(llvm_libs support core irreader)

target_link_libraries(
    KC
    ${llvm_libs}
)

message("LLVM Libs: ${llvm_libs}")