project(any)
cmake_minimum_required(VERSION 2.8)
enable_testing()

set( CMAKE_CXX_STANDARD 14 )

if( ${CMAKE_SYSTEM_NAME} MATCHES Windows ) 
  set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /MP")
elseif(${CMAKE_SYSTEM_NAME} MATCHES Linux)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")
elseif(${CMAKE_SYSTEM_NAME} MATCHES Darwin)
endif()

add_executable(test_any test_any.cpp any.hpp)
add_test(test_any test_any)
