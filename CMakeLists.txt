cmake_minimum_required(VERSION 3.25)
project(example)

set(CMAKE_CXX_STANDARD 20)

if(UNIX)
    if (BUILD_X86_UNIX)
        set(CMAKE_CXX_FLAGS "-m32")
        set(CMAKE_SIZEOF_VOID_P 4)
    endif()
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC")
endif()

add_subdirectory(external/gmod-module-base)
add_subdirectory(src)

set_gmod_suffix_prefix(example)