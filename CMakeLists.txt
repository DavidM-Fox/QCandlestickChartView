cmake_minimum_required(VERSION 3.0.0)

project(qcschart LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(Qt5_DIR "C:\\Qt\\5.15.2\\msvc2019\\lib\\cmake\\Qt5")
set(Qt5Charts_DIR "C:\\Qt\\5.15.2\\msvc2019\\lib\\cmake\\Qt5Charts\\")
find_package(Qt5 COMPONENTS Core Gui Widgets Charts REQUIRED)
find_package(CURL CONFIG REQUIRED)

set(PROJECT_SOURCES
        src/main.cpp
        src/mainwindow.cpp
        src/QCandlestickChart.cpp
        src/avapi.cpp
        inc/mainwindow.h
        inc/mainwindow_ui.h
        inc/QCandlestickChart.h
        inc/avapi.h
)

add_executable(qcschart ${PROJECT_SOURCES})
target_link_libraries(qcschart PRIVATE CURL::libcurl Qt5::Core Qt5::Gui Qt5::Widgets Qt5::Charts)