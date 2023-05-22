file(COPY . DESTINATION ${PROJECT_BINARY_DIR}/libetpan FILES_MATCHING PATTERN "*.h")

add_library(imf OBJECT)

file(GLOB IMF_SOURCE *.c)
target_sources(imf PRIVATE ${IMF_SOURCE})
target_include_directories(imf PRIVATE ${PROJECT_BINARY_DIR} ${PROJECT_BINARY_DIR}/libetpan)

target_link_libraries(etpan PRIVATE imf)