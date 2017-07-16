cmake_minimum_required(VERSION 3.7)
project(ffmpeg)

add_definitions(-D_ISOC99_SOURCE -DHAVE_AV_CONFIG_H)

include_directories(../.)
include_directories(.././)

set(SRC_FILES
        alldevices.c
        avdevice.c
        lavfi.c
        utils.c
        avfoundation.m
)

add_library(avdevice ${SRC_FILES})
