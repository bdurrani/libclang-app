cmake_minimum_required(VERSION 3.16)

project(topProject LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
add_executable(main main.cpp)


add_library(clang STATIC IMPORTED)
set_target_properties(clang PROPERTIES
  IMPORTED_LOCATION "${CMAKE_SOURCE_DIR}/lib/libclang_bundled.a"
  INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_SOURCE_DIR}/include"
)

find_package(ZLIB)

target_link_libraries(main 
  clang             # use static libclang
  Threads::Threads  # -lpthread
  ZLIB::ZLIB        # -lz
  m                 # -lm
  ${CMAKE_DL_LIBS}  # -ldl
)