set(SOURCES main.cpp)
add_library(example SHARED ${SOURCES})
target_link_libraries(example PRIVATE gmod-module-base)