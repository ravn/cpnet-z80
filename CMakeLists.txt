cmake_minimum_required(VERSION 3.20)
project(cpnet-z80 C)

# CLion indexing only.  cpnet-z80 is mostly Z80 assembly (src/) and
# distribution material (dist/, doc/); the only C source is the
# host-side wizcfg utility in util/.  Real builds use the Makefile.

add_executable(wizcfg_index EXCLUDE_FROM_ALL
    util/wizcfg.c
    util/nvram.h
)

target_include_directories(wizcfg_index PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/util
)
