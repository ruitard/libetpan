add_library(etpan dummy.cpp)
target_include_directories(etpan PUBLIC ${PROJECT_BINARY_DIR})

add_subdirectory(main)
add_subdirectory(data-types)
add_subdirectory(low-level)