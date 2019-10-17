cmake_minimum_required(VERSION 3.1)
project(
  VersionInfoSample
  DESCRIPTION "Version Information Sample Program"
  VERSION "1.2.3.4"
  LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

file(GLOB SRCS *.cpp *.cxx *.cc)
add_executable(
  main
  ${SRCS}
  VersionInfo.rc)
