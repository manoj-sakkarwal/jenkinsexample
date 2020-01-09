cmake_minimum_required(VERSION 3.10)
project(jenkinsexample)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_MAKE_PROGRAM 'make')
set(CMAKE_C_COMPILER 'gcc')
set(CMAKE_CXX_COMPILER 'g++')

add_executable(jenkinsexample main.cpp helloWorld.cpp helloWorld.h)

find_package(Qt5 COMPONENTS Core Widgets REQUIRED)

target_compile_definitions(jenkinsexample PRIVATE $<$<OR:$<CONFIG:Debug>,$<CONFIG:RelWithDebInfo>>:QT_QML_DEBUG>)
target_link_libraries(jenkinsexample PRIVATE Qt5::Core Qt5::Widgets)

include(CTest)
add_subdirectory(test)

