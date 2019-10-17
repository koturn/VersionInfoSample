cmake_minimum_required(VERSION 3.1)
project(
  VersionInfoSample
  DESCRIPTION "Version Information Sample Program"
  VERSION "1.2.3.4"
  LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(RCFILE "${CMAKE_CURRENT_BINARY_DIR}/VersionInfo.rc")
include(cmake/GenerateVersionRcFile.cmake)
generate_version_rcfile(
  "${RCFILE}"
  NAME main
  PRODUCT_NAME "Version Information Sample"
  COMPANY_NAME "koturn")

file(GLOB SRCS *.cpp *.cxx *.cc)
add_executable(
  main
  ${SRCS}
  ${RCFILE})
