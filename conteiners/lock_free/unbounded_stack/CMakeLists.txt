cmake_minimum_required(VERSION 3.9)
# add_compile_options(-fsanitize=address)
# add_link_options(-fsanitize=address)
project(unbounded_lock_free_stack)

find_package(Threads REQUIRED)
add_executable(lock_free_stack main.cpp)
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/../../producer_consumer_test)
target_link_libraries(lock_free_stack Threads::Threads)
if(MSVC)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /std:c++17")
endif(MSVC)
set_target_properties(lock_free_stack PROPERTIES
        CXX_STANDART 17
        CXX_STANDART_REQUIRED ON
)