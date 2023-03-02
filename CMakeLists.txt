cmake_minimum_required(VERSION 3.25)
project(gdbstub VERSION 1.0)

add_library(${PROJECT_NAME} STATIC 
    ${PROJECT_SOURCE_DIR}/lib/conn.c
    ${PROJECT_SOURCE_DIR}/lib/packet.c
    ${PROJECT_SOURCE_DIR}/lib/gdbstub.c
    ${PROJECT_SOURCE_DIR}/lib/utils/csum.c
    ${PROJECT_SOURCE_DIR}/lib/utils/translate.c
    )

target_include_directories(${PROJECT_NAME} 
    PUBLIC
    ${PROJECT_SOURCE_DIR}/include/
    )

target_compile_options(${PROJECT_NAME}
    PRIVATE
    -O3
    -Wall
    -Wextra
    -MMD
    )

target_link_options(${PROJECT_NAME}
    PRIVATE
    -O3
    )
