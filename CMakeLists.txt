cmake_minimum_required(VERSION 2.8)

project(tinyrenderer)

set(CMAKE_CXX_STANDARD 14)
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/lib)

include_directories(${PROJECT_SOURCE_DIR}/include)

add_library(tga ${PROJECT_SOURCE_DIR}/src/tgaimage.cpp)
add_library(model ${PROJECT_SOURCE_DIR}/src/model.cpp)

add_executable(main ${PROJECT_SOURCE_DIR}/src/main.cpp)
target_link_libraries(
    main tga model
)