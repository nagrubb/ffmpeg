cmake_minimum_required(VERSION 3.7)
project(ffmpeg)

add_definitions(
        -D_ISOC99_SOURCE
        -DHAVE_AV_CONFIG_H
        -D_FILE_OFFSET_BITS=64
        -D_LARGEFILE_SOURCE
        -DPIC
        -DZLIB_CONST
        -DHAVE_AV_CONFIG_H
)

include_directories(../.)
include_directories(.././)

set(SRC_FILES
        postprocess.c
)

add_library(postproc ${SRC_FILES})
