cmake_minimum_required(VERSION 3.15...3.30)

project(<Name>
                VERSION 1.0
                DESCRIPTION "<Description>"
                LANGUAGES CXX)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Set the default build type if not specified
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug CACHE STRING "Build type" FORCE)
endif()

add_executable(<Name> src/main.cpp)

set(CMAKE_BUILD_TYPE ${CMAKE_BUILD_TYPE} CACHE STRING "Choose Debug or Release" FORCE)

target_compile_features(<Name> PUBLIC cxx_std_11)
set_target_properties(<Name> PROPERTIES CXX_EXTENSIONS OFF)

# find_package(fmt CONFIG REQUIRED)
# target_link_libraries(dsa PRIVATE fmt::fmt)
