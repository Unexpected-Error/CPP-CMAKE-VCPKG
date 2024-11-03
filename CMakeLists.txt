cmake_minimum_required(VERSION 3.15...3.30)

project(<Name>
                VERSION 1.0
                DESCRIPTION "<Description>"
                LANGUAGES CXX)

add_executable(<Name> src/main.cpp
)

target_compile_features(<Name> PUBLIC cxx_std_11)
set_target_properties(<Name> PROPERTIES CXX_EXTENSIONS OFF)