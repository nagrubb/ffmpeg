cmake_minimum_required(VERSION 3.7)
project(ffmpeg)

include_directories(.)
include_directories(./)

add_subdirectory(libavformat)
add_subdirectory(libavcodec)
add_subdirectory(libavutil)
add_subdirectory(libswresample)
add_subdirectory(libavfilter)
add_subdirectory(libavdevice)
add_subdirectory(libpostproc)
add_subdirectory(libswscale)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreImage")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreServices")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreGraphics")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework Security")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework VideoToolbox")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AudioToolbox")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreFoundation")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework VideoDecodeAcceleration")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreMedia")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework CoreVideo")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AVFoundation")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework Foundation")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework OpenGL")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework AppKit")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -framework QuartzCore")

add_executable(ffmpeg
        ffmpeg.c
        cmdutils.c
        ffmpeg_opt.c
        ffmpeg_filter.c
        ffmpeg_hw.c
        ffmpeg_videotoolbox.c
)
target_link_libraries(ffmpeg
        opus
        ass
        avutil
        avdevice
        avformat
        avfilter
        avcodec
        swresample
        postproc
        swscale
        bz2
        iconv
        lzma
        fdk-aac
        freetype
        theora
        vorbis
        vorbisenc
        vpx
        xvidcore
        mp3lame
        m
        x265.116
        x264.148
        z
)
