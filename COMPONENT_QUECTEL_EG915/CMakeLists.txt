# Copyright (c) 2020 ARM Limited. All rights reserved.
# SPDX-License-Identifier: Apache-2.0

add_library(quectel-eg915 STATIC)

target_include_directories(quectel-eg915
    PUBLIC
        .
)

target_sources(quectel-eg915
    PRIVATE
        QUECTEL_EG915.cpp
)

target_link_libraries(quectel-eg915
    PUBLIC
        mbed-core-flags
        mbed-cellular)