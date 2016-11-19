target_sources(xlengine
                PRIVATE
                    "${CMAKE_CURRENT_SOURCE_DIR}/fluidsynthDLL.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/midi.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/oggVorbis.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/sound.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/vocFormat.cpp"
                    "${CMAKE_CURRENT_SOURCE_DIR}/wavFormat.cpp")
