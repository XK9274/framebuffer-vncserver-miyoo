PROJECT(framebuffer-vncserver)
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

# Add these lines to include the headers from libvncserver
include_directories(/root/workspace/libvncserver/include/)
include_directories(/root/workspace/libvncserver/build/include/)

FILE(GLOB SOURCES src/*.c)
ADD_EXECUTABLE(framebuffer-vncserver ${SOURCES})
INSTALL(TARGETS framebuffer-vncserver RUNTIME DESTINATION bin)

# LIBVNC
find_library(LIBVNC NAMES libvncserver vncserver)
target_link_libraries(framebuffer-vncserver ${LIBVNC})

MESSAGE( STATUS "LIBVNC:         " ${LIBVNC} )
