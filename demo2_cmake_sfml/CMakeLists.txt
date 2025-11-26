cmake_minimum_required(VERSION 4.0.0)

project(
    demo2_cmake_sfml
    VERSION 1.0.0
    LANGUAGES C CXX
)

set(CMAKE_CXX_STANDARD          23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS       OFF)

set(DEMO2CORE_PROJECT_TARGET_NAME Demo2Core)

add_subdirectory(Demo2Core)

# We need the FetchContent utility of CMake in order to fetch an external library from sources like github.
include(FetchContent)

set(SFML_LIB_NAME SFML)

# We use the FetchContent utility as follows
FetchContent_Declare(
    ${SFML_LIB_NAME}                                # Name of the utility to fetch
    GIT_REPOSITORY https://github.com/SFML/SFML     # Link to the git repository
    GIT_TAG 2.6.2                                   # The specific tag which we want to include in our project
    GIT_SHALLOW FALSE                               # This fetches all the external dependencies for SFML along with it
)

# NOTE: Install the required dependencies for SFML while running on linux using the following commands
# sudo apt-get update
# sudo apt-get install libopenal-dev
# sudo apt-get install libflac-dev
# sudo apt-get install libvorbis-dev
# sudo apt-get install libudev-dev
FetchContent_MakeAvailable(${SFML_LIB_NAME})

# After this the source code for SFML will be built in the following directory
# build/_deps/sfml-src

# Now after fetching and building sfml with our project, we still need to link the external library with our project
target_link_libraries(${DEMO2CORE_PROJECT_TARGET_NAME} PUBLIC sfml-window)
target_link_libraries(${DEMO2CORE_PROJECT_TARGET_NAME} PUBLIC sfml-graphics)
target_link_libraries(${DEMO2CORE_PROJECT_TARGET_NAME} PUBLIC sfml-audio)
target_link_libraries(${DEMO2CORE_PROJECT_TARGET_NAME} PUBLIC sfml-system)
target_link_libraries(${DEMO2CORE_PROJECT_TARGET_NAME} PUBLIC sfml-network)
