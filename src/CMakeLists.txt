add_library(libanvil)

file(GLOB_RECURSE libanvil_SRC_FILES
    "*.cpp" "*.c")

target_include_directories(libanvil PUBLIC ${libanvil_INCLUDE_DIRS} ${Boost_INCLUDE_DIRS} ${ZLIB_INCLUDE_DIRS})
target_sources(libanvil PUBLIC ${libanvil_SRC_FILES})
target_link_libraries(libanvil Boost::regex ${ZLIB_LIBRARIES})