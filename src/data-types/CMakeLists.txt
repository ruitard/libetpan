file(COPY . DESTINATION ${PROJECT_BINARY_DIR}/libetpan FILES_MATCHING PATTERN "*.h")

add_library(data-types OBJECT)

file(GLOB DATATYPES_SOURCE *.c)
target_sources(data-types PRIVATE ${DATATYPES_SOURCE})
target_include_directories(data-types PRIVATE ${PROJECT_BINARY_DIR} ${PROJECT_BINARY_DIR}/libetpan)

target_link_libraries(etpan PRIVATE data-types)