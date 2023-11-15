cmake_minimum_required(VERSION 3.21)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON) 
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(PROJECT_NAME openNML)

project(${PROJECT_NAME} VERSION 1.0 LANGUAGES C CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

option(ENABLE_QT6 "Enables qt6 package" ON)

if(${CMAKE_BUILD_TYPE} MATCHES "Debug")
    add_definitions(-DDEBUG)
endif()

if(ENABLE_QT6)
    find_package(Qt6 REQUIRED COMPONENTS Core Widgets Gui PrintSupport)
endif()

add_subdirectory(src)
