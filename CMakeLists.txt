cmake_minimum_required(VERSION 3.10.2)
project (hello_world)
 
set(SHARED_LIB_SOURCES src/hello.cpp)
set(EXE_SOURCES src/main.cpp)
set(PROJECT_SOURCE ./include)


add_library(shared_library SHARED ${SHARED_LIB_SOURCES})
target_include_directories(shared_library PUBLIC ${PROJECT_SOURCE})

add_executable(hello_shared_library  ${EXE_SOURCES} )
target_include_directories(hello_shared_library PRIVATE  ${PROJECT_SOURCE})
target_link_libraries(hello_shared_library PRIVATE shared_library)