cmake_minimum_required(VERSION 3.15)
project(PhantomClient)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# No external dependencies
set(CMAKE_FIND_PACKAGE_PREFER_CONFIG ON)

# Source files
set(SOURCES
    src/main.cpp
    src/core/client.cpp
    src/core/protocol.cpp
    src/ui/apple_ui.cpp
    src/net/connection.cpp
)

# Header directories
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/src)

# Main executable
add_executable(phantom-client ${SOURCES})

# macOS specific settings
if(APPLE)
    set_target_properties(phantom-client PROPERTIES
        MACOSX_BUNDLE TRUE
        MACOSX_BUNDLE_GUI_IDENTIFIER "com.phantom.client"
        MACOSX_BUNDLE_BUNDLE_NAME "Phantom Client"
        MACOSX_BUNDLE_BUNDLE_VERSION "1.0.0"
        MACOSX_BUNDLE_SHORT_VERSION_STRING "1.0"
    )
    
    # Link Cocoa framework for native UI
    target_link_libraries(phantom-client "-framework Cocoa")
    target_link_libraries(phantom-client "-framework Foundation")
endif()

# Compiler flags
if(MSVC)
    target_compile_options(phantom-client PRIVATE /W4)
else()
    target_compile_options(phantom-client PRIVATE -Wall -Wextra -Wpedantic)
endif()
