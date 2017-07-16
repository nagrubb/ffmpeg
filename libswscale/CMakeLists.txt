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
        alphablend.c
        gamma.c
        hscale.c
        hscale_fast_bilinear.c
        input.c
        options.c
        output.c
        rgb2rgb.c
        slice.c
        swscale.c
        swscale_unscaled.c
        utils.c
        vscale.c
        x86/hscale_fast_bilinear_simd.c
        x86/rgb2rgb.c
        x86/swscale.c
        x86/yuv2rgb.c
        yuv2rgb.c
)

add_library(swscale ${SRC_FILES})
