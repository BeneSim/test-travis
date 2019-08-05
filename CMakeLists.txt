cmake_minimum_required(VERSION 3.1)

project(test-travis)

find_package(Boost REQUIRED)

add_executable(test-travis src/main.cpp)

install(TARGETS test-travis
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    )

set(CPACK_GENERATOR "ZIP")

include(CPack)
