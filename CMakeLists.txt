cmake_minimum_required(VERSION 3.11)

project(sqlite3)

# set(CMAKE_CXX_STANDARD 17)
add_executable(sqlite3 sqlite3.c shell.c)

if (MSVC)
        target_compile_options(sqlite3 PRIVATE /O2 /MT /EHsc)
else()
        target_compile_options(sqlite3 PRIVATE -O2)
        target_link_libraries(sqlite3 PRIVATE pthread dl m)
endif()