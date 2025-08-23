# -----------------------------------------------------------------------------
#
# This file is part of the µOS++ project (https://micro-os-plus.github.io/).
# Copyright (c) 2025 Liviu Ionescu. All rights reserved.
#
# Permission to use, copy, modify, and/or distribute this software
# for any purpose is hereby granted, under the terms of the MIT license.
#
# If a copy of the license was not distributed with this file, it can
# be obtained from https://opensource.org/licenses/mit.
#
# -----------------------------------------------------------------------------

# This file is intended to be consumed by applications with:
#
# `add_subdirectory("xpacks/@xpack-segger/rtt
# The result is an interface library that can be added to the linker with:
#
# `target_link_libraries(your-target PUBLIC segger::rtt)`

# -----------------------------------------------------------------------------
# Preamble.

# https://cmake.org/cmake/help/v3.20/
cmake_minimum_required(VERSION 3.20)

project(segger-rtt
  DESCRIPTION "SEGGER RTT"
)

if(COMMAND xpack_get_package_name_and_version)
  xpack_get_package_name_and_version("${CMAKE_CURRENT_SOURCE_DIR}/package.json")
  message(VERBOSE "Processing xPack ${PACKAGE_JSON_NAME}@${PACKAGE_JSON_VERSION}...")
endif()

# -----------------------------------------------------------------------------
# The project library definitions.
add_library(segger-rtt-interface INTERFACE EXCLUDE_FROM_ALL)

# -----------------------------------------------------------------------------
# Target settings.
target_include_directories(segger-rtt-interface INTERFACE
  "RTT"
)

target_sources(segger-rtt-interface INTERFACE
  RTT/SEGGER_RTT.c
  RTT/SEGGER_RTT_ASM_ARMv7M.S
  src/diag/trace-segger-rtt.cpp
)

target_compile_definitions(segger-rtt-interface INTERFACE

  # None.
)

target_compile_options(segger-rtt-interface INTERFACE

  # None.
)

target_link_options(segger-rtt-interface INTERFACE

  # None.
)

target_link_libraries(segger-rtt-interface INTERFACE

  # None.
)

if(COMMAND xpack_display_target_lists)
  xpack_display_target_lists(segger-rtt-interface)
endif()

# -----------------------------------------------------------------------------
# Aliases.

# https://cmake.org/cmake/help/v3.20/command/add_library.html#alias-libraries
add_library(segger::rtt ALIAS segger-rtt-interface)
message(VERBOSE "> segger::rtt -> segger-rtt-interface")

# -----------------------------------------------------------------------------
