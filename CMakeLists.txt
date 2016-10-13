cmake_minimum_required(VERSION 3.1)
project(game.libretro.mame)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_package(libretro-mame REQUIRED)

set(DEPLIBS mame)
set(MAME_CUSTOM_BINARY ${MAME_LIB}
                       ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} MAME DEPLIBS)
