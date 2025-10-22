cmake_minimum_required(VERSION 3.15)
project(mlib C)

file(GLOB_RECURSE MLIB_SRC_FILES "${PROJECT_SOURCE_DIR}/*.c")
add_library(${PROJECT_NAME} STATIC ${MLIB_SRC_FILES})
