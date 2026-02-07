cmake_minimum_required(VERSION 3.30)

project(entt_pong LANGUAGES C CXX)

set(target ${PROJECT_NAME})
add_executable(${target})
target_compile_features(${target} PRIVATE c_std_23 cxx_std_26)

find_package(EnTT CONFIG REQUIRED)
target_link_libraries(${target} PRIVATE EnTT::EnTT)
find_package(SDL2 CONFIG REQUIRED)
target_link_libraries(${target} PRIVATE SDL2::SDL2)
find_package(PkgConfig)
pkg_check_modules(SDL2_GFX REQUIRED IMPORTED_TARGET SDL2_gfx)
target_link_libraries(${target} PUBLIC PkgConfig::SDL2_GFX)

add_subdirectory(EnttPong)