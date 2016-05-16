project(game.libretro.mame)

cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(Kodi REQUIRED)
find_package(libretro-mame REQUIRED)

set(DEPLIBS mame)
set(MAME_CUSTOM_BINARY ${MAME_LIB}
                       ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX} mame)

build_addon(${PROJECT_NAME} MAME DEPLIBS)
