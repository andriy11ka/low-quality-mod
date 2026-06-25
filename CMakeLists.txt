cmake_minimum_required(VERSION 3.21)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_OSX_ARCHITECTURES "arm64")
if (WIN32)
    add_definitions(-DNOMINMAX)
endif()

project(LowQuality VERSION 1.0.0)

include(FetchContent)

FetchContent_Declare(
    geode
    URL https://github.com/geode-sdk/geode/releases/download/v5.7.1/geode-sdk.zip
)
FetchContent_MakeAvailable(geode)

file(GLOB SOURCES
    src/*.cpp
)

add_library(${PROJECT_NAME} SHARED ${SOURCES})
target_link_libraries(${PROJECT_NAME} geode-sdk)
create_geode_file(${PROJECT_NAME})
