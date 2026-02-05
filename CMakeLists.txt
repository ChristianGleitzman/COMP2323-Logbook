cmake_minimum_required(VERSION 3.13)

# 1. Initialize the SDK
include($ENV{PICO_SDK_PATH}/pico_sdk_init.cmake)

# 2. Project Definition
project(comp2323_logbook C CXX ASM)

# 3. Initialize the Pico SDK
pico_sdk_init()

# 4. Add the Executable (Task 1)
# This links your 'example.c' to the build system
add_executable(week01_blink
    src/week-01/example.c
)

# 5. Link Libraries (Standard IO and Boot capability)
target_link_libraries(week01_blink pico_stdlib)

# 6. Enable USB/UART Output (Crucial for debugging later)
pico_enable_stdio_usb(week01_blink 1)
pico_enable_stdio_uart(week01_blink 0)

# 7. Create the .uf2 file (The actual file you drag-and-drop to the Pico)
pico_add_extra_outputs(week01_blink)
