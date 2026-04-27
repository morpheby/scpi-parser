cmake_minimum_required(VERSION 3.16)

if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    project(scpi_parser C)
endif()

file(GLOB _SCPI_SRC "${CMAKE_CURRENT_SOURCE_DIR}/libscpi/src/*.c")
add_library(ch32_scpi STATIC ${_SCPI_SRC})
target_include_directories(ch32_scpi PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/libscpi/inc")
# Note: SCPI_USER_CONFIG must be defined by the consuming project if a custom config is needed
