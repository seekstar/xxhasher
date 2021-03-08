cmake_minimum_required(VERSION 3.2)
project(xxhasher)

IF (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING
        "Choose the type of build, options are: Debug Release RelWithDebInfo MinSizeRel." FORCE)
ENDIF()
add_compile_options(-Wall -Wextra -fexceptions)
IF (CMAKE_BUILD_TYPE STREQUAL "Debug")
    ADD_DEFINITIONS(-DDEBUG)
ENDIF()

aux_source_directory(src SRCS)
add_library(xxhasher ${SRCS})
target_include_directories(xxhasher
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)
