project(pge_game)

# All sources that also need to be tested in unit tests go into a static library
#add_library(game_lib STATIC olcPEGX_Console.h)
add_library(game_lib INTERFACE)
target_include_directories(game_lib INTERFACE ${CMAKE_CURRENT_SOURCE_DIR} )
target_compile_features(game_lib INTERFACE cxx_std_17)
target_link_libraries(game_lib INTERFACE pge_lib)

# The main program
add_executable(game game.cpp)
target_link_libraries(game PRIVATE pge_lib game_lib)
