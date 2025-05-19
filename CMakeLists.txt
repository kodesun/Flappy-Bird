cmake_minimum_required(VERSION 3.10)
project(Flappy-Bird)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 11)

find_package(SFML 2.5 COMPONENTS window audio graphics network REQUIRED)

file(GLOB SOURCE_FILES 
    "src/*.cpp"
    "src/managers/*.cpp"
    "src/machine/*.cpp"
    "src/objects/*.cpp"
    "src/states/*.cpp"
)

add_executable(${PROJECT_NAME} ${SOURCE_FILES})

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_link_libraries(${PROJECT_NAME} sfml-graphics sfml-window sfml-audio sfml-network)
