cmake_minimum_required(VERSION 3.15)

project(lien_strutils LANGUAGES CXX)

option(LIEN_BUILD_TESTS "Build tests" ON)

add_library(lien_strutils src/strutils.cpp)
set_target_properties(lien_strutils PROPERTIES
    CXX_STANDARD 17
    CXX_STANDARD_REQUIRED ON
    CXX_EXTENSIONS OFF
) 

target_include_directories(lien_strutils PUBLIC include)

if(LIEN_BUILD_TESTS)
    add_subdirectory(test)
endif()