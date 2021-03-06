cmake_minimum_required(VERSION 3.6)
project(MagicCLITool)

set(CMAKE_CXX_STANDARD 14)

find_package(LLVM REQUIRED CONFIG)
message(STATUS "Using LLVM version ${LLVM_VERSION}")

include_directories(${LLVM_INCLUDE_DIRS})
link_directories(${LLVM_LIBRARY_DIRS})

add_definitions(${LLVM_DEFINITIONS})
if(NOT ${LLVM_ENABLE_RTTI})
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-rtti")
endif()

list(APPEND CMAKE_MODULE_PATH ${LLVM_CMAKE_DIR})
include(AddLLVM)

set(LLVM_LINK_COMPONENTS
    Analysis
    Support)

add_llvm_executable(magic-cli
  main.cpp)
