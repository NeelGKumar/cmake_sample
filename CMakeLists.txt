cmake_minimum_required (VERSION 2.8.11)
project(test)
add_executable(hello hello.cpp)

set(ARCHIVE_OUTPUT_DIRECTORY  subproject1/lib)
add_subdirectory(subproject1)
 
include_directories(subproject2/include)
set(Sources subproject1/src/source2.cpp hello2.cpp)
add_executable(hello2 ${Sources})

include_directories(external/include)
link_directories( external/lib )
add_executable(hello3 hello.cpp)
target_link_libraries(hello3 external.lib)
