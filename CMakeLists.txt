cmake_minimum_required(VERSION 3.13)

project(hello_world)

add_executable(hello_world src/main.c)

# Tell IDF build to link against this target.
set(IDF_PROJECT_EXECUTABLE hello_world)

# Add FreeRTOS as a subdirectory. AFR_BOARD tells which board to target.
set(AFR_BOARD espressif.esp32_devkitc CACHE INTERNAL "")
add_subdirectory(amazon-freertos)
