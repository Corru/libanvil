#
# 
#
add_library(libanvil)


# ------------------------------------------------------- #


# Look for default C/C++ source files
file(GLOB_RECURSE libanvil_SRC_FILES
    "*.hpp" "*.cpp" "*.h" "*.c")

    
# ------------------------------------------------------- #


# Configure common target settings
target_include_directories(libanvil PUBLIC ${libanvil_INCLUDE_DIRS} ${Boost_INCLUDE_DIRS} ${ZLIB_INCLUDE_DIRS})
target_sources(libanvil PRIVATE ${libanvil_SRC_FILES})
target_link_libraries(libanvil Boost::regex ${ZLIB_LIBRARIES})

# Disable "lib" prefix in library name 'cause it already have it
set_target_properties(libanvil PROPERTIES PREFIX "")