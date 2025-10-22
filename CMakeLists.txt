cmake_minimum_required(VERSION 3.15)
project(mimirc C)

set(CMAKE_C_STANDARD 17)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Enable strict warnings (adjust for MSVC vs GCC/Clang)
if (MSVC)
    add_compile_options(/W4 /WX)
else()
    add_compile_options(-Wall -Wextra -Werror)
endif()

# Collect all .c files under compiler/
file(GLOB_RECURSE SRC_FILES "${CMAKE_SOURCE_DIR}/compiler/*.c")
add_subdirectory(compiler/lib)
add_executable(mimirc ${SRC_FILES})

# Output binary into build/
set_target_properties(mimirc PROPERTIES
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}"
)
