cmake_minimum_required(VERSION 3.7)
project(ffmpeg)

add_definitions(-D_ISOC99_SOURCE -DHAVE_AV_CONFIG_H)

include_directories(../.)
include_directories(.././)

set(SRC_FILES
        audioconvert.c
        dither.c
        options.c
        rematrix.c
        resample.c
        resample_dsp.c
        swresample.c
        swresample_frame.c
        x86/audio_convert_init.c
        x86/rematrix_init.c
        x86/resample_init.c
)

#X86ASM	libswresample/x86/audio_convert.o
#X86ASM	libswresample/x86/rematrix.o
#X86ASM	libswresample/x86/resample.o

add_library(swresample ${SRC_FILES})
