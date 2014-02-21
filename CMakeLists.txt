project(gameclient.mame)

cmake_minimum_required(VERSION 2.6)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(xbmc REQUIRED)

include(ExternalProject)

externalproject_add(mame 
                    GIT_REPOSITORY https://github.com/libretro/mame078-libretro
                    GIT_TAG d980525
                    PREFIX mame
                    CONFIGURE_COMMAND ""
                    INSTALL_COMMAND ""
                    BUILD_COMMAND make
                    BUILD_IN_SOURCE 1)

set(MAME_CUSTOM_BINARY ${PROJECT_BINARY_DIR}/mame/src/mame/mame078_libretro${CMAKE_SHARED_LIBRARY_SUFFIX}
                       mame078_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} mame)

build_addon(gameclient.mame MAME DEPLIBS)
add_dependencies(gameclient.mame mame)
