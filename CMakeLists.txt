cmake_minimum_required(VERSION 3.18)
project(TCS34725_LIB CXX)

add_library(TCS34725_LIB STATIC
    Adafruit_TCS34725.cpp
    Adafruit_TCS34725.hpp
)

target_include_directories(TCS34725_LIB PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/../Drivers/STM32F3xx_HAL_Driver/Inc
    ${CMAKE_CURRENT_SOURCE_DIR}/../Drivers/CMSIS/Include
    ${CMAKE_CURRENT_SOURCE_DIR}/../Drivers/CMSIS/Device/ST/STM32F3xx/Include
)

target_link_libraries(TCS34725_LIB PUBLIC
    HAL::STM32::F3::GPIO
    HAL::STM32::F3::I2C
)
