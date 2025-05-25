# Generated Cmake NMEA2000_PICO library for use with ttlappalainen - NMEA2000
#   https://github.com/forcel0/NMEA2000_PICO.git
#   https://github.com/ttlappalainen/NMEA2000.git

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# debuggin on
#add_definitions(-DDEBUG_MCP_CAN_SPEED)
#add_definitions(-DPICO_OPTIMIZED_DEBUG=1)

# NMEA2000_PICO library
add_library(NMEA2000_PICO 
    # Library sources
    ./mcp2515.cpp
    ./NMEA2000_PICO.cpp
    # nmea2000 library sources
    ../../NMEA/src/N2kMsg.cpp
    ../../NMEA/src/N2kStream.cpp
    ../../NMEA/src/N2kMessages.cpp
    ../../NMEA/src/N2kTimer.cpp
    ../../NMEA/src/Seasmart.cpp
    ../../NMEA/src/N2kDeviceList.cpp
    ../../NMEA/src/N2kGroupFunction.cpp
    ../../NMEA/src/N2kGroupFunctionDefaultHandlers.cpp
    ../../NMEA/src/N2kMaretron.cpp
    ../../NMEA/src/NMEA2000.cpp
)

target_include_directories(NMEA2000_PICO PUBLIC ./)
target_include_directories(NMEA2000_PICO PUBLIC ../../NMEA/src/)

# Add any user requested libraries
target_link_libraries(NMEA2000_PICO
    pico_stdlib
    hardware_spi
)
