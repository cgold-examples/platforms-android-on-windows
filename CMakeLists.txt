cmake_minimum_required(VERSION 3.4)

### Emulate toolchain {
set(_expected_platform_module "${CMAKE_ROOT}/Modules/Platform/VCMDDAndroid.cmake")

if(NOT EXISTS "${_expected_platform_module}")
  message(
      FATAL_ERROR
      "File not found:\n  ${_expected_platform_module}\n"
      "You are using non-patched CMake version!"
  )
endif()

set(CMAKE_SYSTEM_NAME "VCMDDAndroid")
### }

project(foo)

add_library(foo foo.cpp)
