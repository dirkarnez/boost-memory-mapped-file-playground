cmake_minimum_required(VERSION 3.18)

project("boost-memory-mapped-file-playground")

find_package(Boost COMPONENTS iostreams REQUIRED)

if(Boost_FOUND)
    message(STATUS "YES")
else()
    message(STATUS "NO")
endif()

add_executable(${PROJECT_NAME}
    "src/main.cpp"
)

target_link_libraries(${PROJECT_NAME} ${Boost_LIBRARIES})
target_link_options(${PROJECT_NAME} PRIVATE "-static")
