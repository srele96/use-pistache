cmake_minimum_required(VERSION 3.6)
project("use-pistache")

# -----------------------------------------------------------------------------
# Finds the downloaded pistache headers and static library
# located at:
# - /usr/include
# - /usr/lib
# 
# For example, on my system:
# 
# /usr/lib/x86_64-linux-gnu/pkgconfig/libpistache.pc
# /usr/lib/x86_64-linux-gnu/libpistache.so.0.4
# /usr/lib/x86_64-linux-gnu/libpistache.a
# /usr/lib/x86_64-linux-gnu/libpistache.so
# /usr/lib/x86_64-linux-gnu/libpistache.so.0.4.26
# 
# And
# 
# /usr/include/pistache
# -----------------------------------------------------------------------------

find_package(PkgConfig)
pkg_check_modules(Pistache REQUIRED IMPORTED_TARGET libpistache)

add_executable(${PROJECT_NAME} main.cpp)
target_link_libraries(${PROJECT_NAME} PkgConfig::Pistache)
