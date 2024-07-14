cmake_minimum_required(VERSION 3.10)

project(UndoRedoProject)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(UndoRedoTest UndoRedoGTEST.cpp UndoRedo.h)

include(FetchContent)
FetchContent_Declare(
        googletest
        URL https://github.com/google/googletest/archive/refs/tags/release-1.12.1.zip
)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

target_link_libraries(UndoRedoTest gtest_main)

enable_testing()

add_test(NAME UndoRedoTest COMMAND UndoRedoTest)
