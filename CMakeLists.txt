cmake_minimum_required(VERSION 3.7)
project(SDLGameboy)

find_package(SDL2 REQUIRED)

include_directories(${PROJECT_NAME} 
	${SDL2_INCLUDE_DIRS}
	include/
	external/incbin/
)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread -std=c++14")

add_executable(${PROJECT_NAME}
	src/main.cpp
	src/bus.cpp
	src/cart.cpp
	src/opcodes.cpp
	src/cpu.cpp
	src/ppu.cpp	
	src/IO.cpp
	src/MBC1.cpp
)

target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARIES})