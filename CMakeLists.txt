cmake_minimum_required(VERSION 2.6)
project(SOIL)

if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

include_directories(inc)

FILE(GLOB SOIL_c src/*.c)
FILE(GLOB SOIL_h inc/SOIL/*.h)

ADD_LIBRARY( soil STATIC ${SOIL_c} )

install( TARGETS soil ARCHIVE DESTINATION "lib" )
install( FILES ${SOIL_h} DESTINATION "include/SOIL" )
