cmake_minimum_required(VERSION 3.1)
project(xlengine)

set(CMAKE_CXX_STANDARD 98)

find_package(OpenGL REQUIRED)
find_package(OpenAL REQUIRED)
find_package(Freetype REQUIRED)
find_package(X11 REQUIRED)
find_package(Threads REQUIRED)

add_executable(xlengine "")

if(WIN32)
    target_sources(xlengine PRIVATE "stdafx.cpp")
else()
    target_include_directories(xlengine
                                PRIVATE
                                    ${X11_INCLUDE_DIR})
    target_link_libraries(xlengine
                                    ${CMAKE_DL_LIBS}
                                    ${X11_LIBRARIES} ${X11_Xrandr_LIB})
endif()

target_include_directories(xlengine
                            PRIVATE
                                ${OPENGL_INCLUDE_DIR}
                                ${OPENAL_INCLUDE_DIR}
                                ${FREETYPE_INCLUDE_DIRS})

target_link_libraries(xlengine
                        ${OPENGL_LIBRARIES}
                        ${OPENAL_LIBRARY}
                        ${FREETYPE_LIBRARIES}
                        ${CMAKE_THREAD_LIBS_INIT}
                        WildMidi
                        IL
                        vorbisfile)

install(TARGETS xlengine RUNTIME DESTINATION bin)

add_subdirectory(OS/)
add_subdirectory(XLEngine/)
