cmake_minimum_required(VERSION 2.8)
project(exupstream2)

################################
# Metadata
################################

set(EXUPSTREAM2_VERSION "0.0.1")

################################
# Locate source
################################

file(GLOB_RECURSE INCLUDES include/*.h)
file(GLOB_RECURSE SRC src/*.cpp)

include_directories(include)

################################
# Build targets
################################

add_library(exupstream2 SHARED
    ${SRC}
    ${INCLUDES})

################################
# Export library
################################

export_project(
    NAME libexupstream2
    INCLUDES ${CMAKE_CURRENT_LIST_DIR}/include
    LIBS exupstream2
    VERSION ${EXUPSTREAM2_VERSION}
)

