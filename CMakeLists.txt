
cmake_minimum_required(VERSION 3.16)

project(PacketAnalyzer VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(Threads REQUIRED)

set(SOURCES
    src/main_dpi.cpp
    src/dpi_engine.cpp
    src/pcap_reader.cpp
    src/packet_parser.cpp
    src/sni_extractor.cpp
    src/types.cpp
    src/connection_tracker.cpp
    src/load_balancer.cpp
    src/fast_path.cpp
    src/rule_manager.cpp
)

add_executable(dpi_engine ${SOURCES})

target_include_directories(dpi_engine PRIVATE include)

target_link_libraries(dpi_engine PRIVATE Threads::Threads)
