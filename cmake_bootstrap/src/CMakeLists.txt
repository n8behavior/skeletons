project(main_prog)

# All sources that also need to be tested in unit tests go into a static library
add_library(main_lib STATIC main.hpp)
target_include_directories(main_lib INTERFACE ${CMAKE_CURRENT_SOURCE_DIR} )
target_compile_features(main_lib INTERFACE cxx_std_17)
set_target_properties(main_lib PROPERTIES LINKER_LANGUAGE CXX)
#target_link_libraries(main_lib INTERFACE )

# The main program
add_executable(main_prog main.cpp)
target_link_libraries(main_prog PRIVATE main_lib)
