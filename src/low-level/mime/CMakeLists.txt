file(COPY . DESTINATION ${PROJECT_BINARY_DIR}/libetpan FILES_MATCHING PATTERN "*.h")

add_library(mime OBJECT)

file(GLOB MIME_SOURCE *.c)
target_sources(mime PRIVATE ${MIME_SOURCE})
target_include_directories(mime PRIVATE ${PROJECT_BINARY_DIR} ${PROJECT_BINARY_DIR}/libetpan)

target_link_libraries(etpan PRIVATE mime)