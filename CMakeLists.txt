cmake_minimum_required(VERSION 3.24)
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

set(CMAKE_CONFIGURATION_TYPES Release Debug)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/bin/release)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/bin/debug)
set(CMAKE_RUNTIME_LIBRARY_DIRECTORY_RELEASE ${CMAKE_BINARY_DIR}/bin/release)
set(CMAKE_RUNTIME_LIBRARY_DIRECTORY_DEBUG ${CMAKE_BINARY_DIR}/bin/debug)

set_gmod_suffix_prefix(example)