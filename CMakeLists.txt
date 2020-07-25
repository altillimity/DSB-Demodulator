cmake_minimum_required (VERSION 3.0.0)

list(APPEND CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake")

project (demodPOES)
set(PROJECT_VERSION 1.0)
file(GLOB_RECURSE DSB_DECODER_CPPS src/*.c)
add_executable(demodPOES ${DSB_DECODER_CPPS})
target_include_directories(demodPOES PUBLIC ${CMAKE_SOURCE_DIR}/src)

find_package (Threads)
target_link_libraries (demodPOES PUBLIC ${CMAKE_THREAD_LIBS_INIT})
target_link_libraries (demodPOES PUBLIC "m")

install(TARGETS demodPOES DESTINATION bin)