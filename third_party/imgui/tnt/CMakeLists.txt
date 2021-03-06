cmake_minimum_required(VERSION 3.10)
project(imgui)

set(OUR_DIR ${CMAKE_CURRENT_SOURCE_DIR}/..)

set(TARGET              imgui)

set(SRC_DIR             ${OUR_DIR})
set(PUBLIC_HDR_DIR      ${OUR_DIR}/include)
set(PRIVATE_HDR_DIR     ${OUR_DIR})

set(PUBLIC_HDRS
    ${PUBLIC_HDR_DIR}/imconfig.h
    ${PUBLIC_HDR_DIR}/imgui.h
)

set(PRIVATE_HDRS
    ${PRIVATE_HDR_DIR}/imgui_internal.h
    ${PRIVATE_HDR_DIR}/stb_rect_pack.h
    ${PRIVATE_HDR_DIR}/stb_textedit.h
    ${PRIVATE_HDR_DIR}/stb_truetype.h
)

set(SRCS
    ${SRC_DIR}/imgui.cpp
    ${SRC_DIR}/imgui_demo.cpp
    ${SRC_DIR}/imgui_draw.cpp
)

add_library(${TARGET} STATIC ${PRIVATE_HDRS} ${PUBLIC_HDRS} ${SRCS})

target_include_directories(${TARGET} PUBLIC ${PUBLIC_HDR_DIR} ${PRIVATE_HDR_DIR})
