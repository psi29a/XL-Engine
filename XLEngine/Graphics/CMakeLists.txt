target_sources(xlengine
                PRIVATE
                    "${CMAKE_CURRENT_SOURCE_DIR}/graphicsDevice.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/graphicsDeviceList.cpp")
                    
if(WIN32)
    target_sources(xlengine PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/Win32/graphicsDeviceGL_Win32.cpp")
else()
    target_sources(xlengine PRIVATE "${CMAKE_CURRENT_SOURCE_DIR}/Linux/graphicsDeviceGL_Linux.cpp")
endif()

add_subdirectory(CommonGL/)
add_subdirectory(Devices/)
