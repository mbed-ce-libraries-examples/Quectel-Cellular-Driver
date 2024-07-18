# Copyright (c) 2020 ARM Limited. All rights reserved.
# SPDX-License-Identifier: Apache-2.0

add_library(quectel-ec2x STATIC)

target_include_directories(quectel-ec2x
    PUBLIC
        .
)

target_sources(quectel-ec2x
    PRIVATE
        QUECTEL_EC2X.cpp
)

target_link_libraries(quectel-ec2x
	PUBLIC
		mbed-core-flags
	    mbed-cellular)