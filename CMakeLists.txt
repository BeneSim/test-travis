cmake_minimum_required(VERSION 3.1)

project(test-travis)

find_package(Boost REQUIRED COMPONENTS system)
find_package(Threads REQUIRED)

add_executable(test-travis src/main.cpp)

target_compile_features(test-travis PRIVATE cxx_std_17)
target_link_libraries(test-travis Threads::Threads ${Boost_LIBRARIES})

install(TARGETS test-travis
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    )

set(CPACK_GENERATOR "ZIP")

include(CPack)
