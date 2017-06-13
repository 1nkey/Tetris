cmake_minimum_required (VERSION 2.6)

project (Tetris)

set(EXECUTABLE_NAME "tetris")
add_executable(${EXECUTABLE_NAME} source/test.cpp)

set(CMAKE_MODULE_PATH "/usr/share/SFML/cmake/Modules")

find_package(SFML 2 REQUIRED graphics window system)
if(SFML_FOUND)
  include_directories(${SFML_INCLUDE_DIR})
  target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES} ${SFML_DEPENDENCIES})
endif()

install(TARGETS ${EXECUTABLE_NAME} DESTINATION bin)
