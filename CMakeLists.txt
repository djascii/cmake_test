cmake_minimum_required(VERSION 3.10)

project(cmake_test)

# set(CMAKE_CXX_COMPILER /usr/bin/g++-15)
set(CMAKE_CXX_STANDARD 23)


add_executable(cmake_test src/main.cpp)

add_subdirectory(libs/MyLib)
add_subdirectory(external/glfw)

target_include_directories(cmake_test PRIVATE libs/MyLib external/glfw/include)
target_link_libraries(cmake_test PRIVATE MyLib glfw)
