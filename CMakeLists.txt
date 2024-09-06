cmake_minimum_required(VERSION 3.20)
project(pnm)

option(PNM_BUILD_SAMPLES "Builds the sample applications" OFF)
option(PNM_BUILD_TEST "Builds the tests" OFF)

add_library(pnm INTERFACE)
target_include_directories(pnm INTERFACE ${CMAKE_CURRENT_LIST_DIR}/include)

if (PNM_BUILD_TEST)
  enable_testing()
  if (PNM_BUILD_TEST)
    add_subdirectory(test)
  endif ()
endif ()

if (PNM_BUILD_SAMPLES)
  add_subdirectory(sample)
endif ()

