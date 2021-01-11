# set(libanvil_SRC_DIR      "${CMAKE_CURRENT_SOURCE_DIR}/src")
# set(libanvil_INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}/include")

# find_package(Boost REQUIRED COMPONENTS regex)

# add_subdirectory(src)

# ------------------------------------------------------- #


cmake_minimum_required(VERSION 3.0)
project(libanvil VERSION 1.0.0 LANGUAGES CXX)


# ------------------------------------------------------- #


set(libanvil_INCLUDE_DIRS "${CMAKE_CURRENT_SOURCE_DIR}/include" PARENT_SCOPE)
set(libanvil_LIBRARIES    libanvil                              PARENT_SCOPE)


# ------------------------------------------------------- #


if (NOT Boost_REGEX_FOUND)
    find_package(Boost REQUIRED COMPONENTS regex)
endif()


# ------------------------------------------------------- #


add_subdirectory(src)