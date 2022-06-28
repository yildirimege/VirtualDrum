# -------------------------------------------------------------------------------------------------
# Set Library (VirtualDrumLib)
# -------------------------------------------------------------------------------------------------
project(VirtualDrumLib)

# -------------------------------------------------------------------------------------------------
# Set Project Headers
# -------------------------------------------------------------------------------------------------
set(${PROJECT_HEADERS}
    "${CMAKE_CURRENT_LIST_DIR}/src/temp.h"
    )

# -------------------------------------------------------------------------------------------------
# Set Project Sources
# -------------------------------------------------------------------------------------------------
set(${PROJECT_SOURCES}
    "${CMAKE_CURRENT_LIST_DIR}/src/temp.cpp"
    )

# -------------------------------------------------------------------------------------------------
# Add a library with the above sources
# -------------------------------------------------------------------------------------------------
add_library(${PROJECT_NAME}
    ${PROJECT_HEADERS}
    ${PROJECT_SOURCES}

    "src/sources/temp.cpp"
    "src/headers/temp.h"



   "src/sources/drum.cpp" "src/sources/image_loader.cpp" "src/sources/gui.cpp" "src/sources/event_handler.cpp" "src/headers/drum.h" "src/headers/event_handler.h" "src/headers/gui.h" "src/headers/image_loader.h" "src/headers/glui.h")


# -------------------------------------------------------------------------------------------------
# Include Path
# -------------------------------------------------------------------------------------------------
target_include_directories(
    ${PROJECT_NAME} PUBLIC
        "${CMAKE_CURRENT_LIST_DIR}/src"
  )


# -------------------------------------------------------------------------------------------------
# Set Alias of Library to reach from parent executeable
# -------------------------------------------------------------------------------------------------
add_library(sub::VirtualDrumLib ALIAS ${PROJECT_NAME})
