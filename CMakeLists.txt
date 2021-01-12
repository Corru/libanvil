cmake_minimum_required(VERSION 3.0)
project(libanvil VERSION 1.0.0 LANGUAGES CXX)


# ------------------------------------------------------- #


set(libanvil_INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}/include" PARENT_SCOPE)
set(libanvil_LIBRARIES    libanvil                               PARENT_SCOPE)

get_directory_property(_hasParentScope PARENT_DIRECTORY)
if (NOT _hasParentScope)
    set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/lib)
    set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin/lib)
endif()
unset(_hasParentScope)


# ------------------------------------------------------- #


if (NOT Boost_REGEX_FOUND)
    find_package(Boost REQUIRED COMPONENTS regex)
endif()

if (NOT ZLIB_FOUND)
    find_package(ZLIB REQUIRED)
endif()


# ------------------------------------------------------- #


add_subdirectory(src)