cmake_minimum_required(VERSION 3.13)

# Include the Pico SDK
include(pico_sdk_import.cmake)

# Define the project
project(test_project C CXX ASM)

# Set the PICO_BOARD variable
set(PICO_BOARD pico_w)

# Set the C and C++ standards
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialize the Pico SDK
pico_sdk_init()

# Create the executable
add_executable(blink blink.c)

# Enable USB and UART for the executable
pico_enable_stdio_usb(blink 1)
pico_enable_stdio_uart(blink 1)

# Add extra outputs (e.g., UF2 file)
pico_add_extra_outputs(blink)

# Link the necessary libraries
target_link_libraries(blink pico_stdlib pico_cyw43_arch_none)


