cmake_minimum_required(VERSION 3.27)
project(cacti)

set(CMAKE_CXX_STANDARD 23)

include_directories("include")

file(GLOB_RECURSE SOURCES "src/*.cc")

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS}")
add_compile_definitions(NTHREADS=6)
add_executable(cacti main.cc ${SOURCES})
#add cfg files to the build directory: all file in sample_config_files
file(COPY sample_config_files DESTINATION ${CMAKE_BINARY_DIR})

#copy tech_params file to the build director
file(COPY tech_params DESTINATION ${CMAKE_BINARY_DIR})

