cmake_minimum_required(VERSION 3.9)
project(untitled)

set(CMAKE_CXX_STANDARD 17)
find_package (Threads)
find_package(OpenSSL 1.0.2 REQUIRED)

find_package(Boost REQUIRED COMPONENTS system thread log program_options chrono)
add_executable(untitled main.cpp)
include_directories(${Boost_INCLUDDIR})
target_link_libraries(untitled cpprest)
target_link_libraries(untitled  ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries(untitled  ${Boost_LIBRARIES})
message("openssl libs: "${OPENSSL_FOUND})
target_link_libraries(untitled  ${OPENSSL_LIBS} ${OPENSSL_CRYPTO_LIBRARY} ${OPENSSL_SSL_LIBRARY})

