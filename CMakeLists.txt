cmake_minimum_required(VERSION 3.7 FATAL_ERROR)
project(poe_stash_indexer)

set(CMAKE_CXX_STANDARD 11)

include_directories(${PROJECT_SOURCE_DIR}/lib)

add_executable(indexer
        lib/CFG_reader.cpp
        lib/Misc.cpp
        main.cpp)

target_link_libraries(indexer
        pthread
        curl
        mysqlcppconn)

configure_file(config.cfg config.cfg COPYONLY)
