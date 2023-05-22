cmake_minimum_required(VERSION 3.20.0)
project(libetpan VERSION 1.9.4)

include(CTest)
enable_testing()

INCLUDE(CheckIncludeFile)
CHECK_INCLUDE_FILE("inttypes.h" HAVE_INTTYPES_H)
CHECK_INCLUDE_FILE("unistd.h" HAVE_UNISTD_H)
CHECK_INCLUDE_FILE("sys/mman.h" HAVE_SYS_MMAN_H)

add_compile_definitions(HAVE_CONFIG_H)
configure_file(config.h.cmake.in ${PROJECT_BINARY_DIR}/config.h)

add_subdirectory(src)
add_subdirectory(tests)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
