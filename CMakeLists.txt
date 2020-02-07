cmake_minimum_required(VERSION 3.15.0)

add_library(pcg-c STATIC)

aux_source_directory(./src PCG_C_SRCS)
target_sources(pcg-c PRIVATE ${PCG_C_SRCS})
target_include_directories(pcg-c PUBLIC include)

if (MSVC)
    target_compile_options(pcg-c PUBLIC /utf-8 /permissive-)
endif()
