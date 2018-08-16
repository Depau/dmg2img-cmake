cmake_minimum_required(VERSION 3.4)

project(dmg2img)
set(CMAKE_C_STANDARD 11)

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

target_link_libraries(dmg2img -lz -lbz2)


project(vfdecrypt)
set(CMAKE_C_STANDARD 11)

include_directories(src)
add_executable(vfdecrypt
        src/vfdecrypt.c
        src/vfdecrypt.h)

target_link_libraries(vfdecrypt -lcrypto)
