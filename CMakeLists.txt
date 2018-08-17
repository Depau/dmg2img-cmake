cmake_minimum_required(VERSION 3.4)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -pie")
add_compile_options(-fPIE)
set(CMAKE_C_STANDARD 11)

project(dmg2img)
include_directories(src)
add_executable(dmg2img
        src/adc.c
        src/adc.h
        src/base64.c
        src/base64.h
        src/dmg2img.c
        src/dmg2img.h
        src/gpt.h
        src/mntcmd.h)

target_link_libraries(dmg2img z bz2)


project(vfdecrypt)
add_compile_options(-fPIE)
include_directories(src)
add_executable(vfdecrypt
        src/vfdecrypt.c
        src/vfdecrypt.h)

target_link_libraries(vfdecrypt crypto)
