cmake_minimum_required(VERSION 3.17)

project(TCS34725_LIB CXX)

# Define the library target
add_library(TCS34725_LIB STATIC
    Adafruit_TCS34725.cpp
    Adafruit_TCS34725.hpp
)

# Specify the include directories for the library and dependencies
target_include_directories(TCS34725_LIB PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${stm32-cmake_SOURCE_DIR}/Drivers/STM32F3xx_HAL_Driver/Inc
    ${stm32-cmake_SOURCE_DIR}/Drivers/CMSIS/Include
    ${stm32-cmake_SOURCE_DIR}/Drivers/CMSIS/Device/ST/STM32F3xx/Include
)

# Link required libraries
find_package(HAL COMPONENTS I2C REQUIRED)
target_link_libraries(TCS34725_LIB PUBLIC
    HAL::STM32::F3::I2C
)
