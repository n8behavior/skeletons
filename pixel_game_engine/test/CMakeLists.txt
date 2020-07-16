project(game_tests)

# The test program
add_executable(tests testmain.cpp)
target_link_libraries(tests PRIVATE catch pge_lib )
target_compile_features(tests PUBLIC cxx_std_17)
target_compile_definitions(tests PRIVATE CATCH_CONFIG_CONSOLE_WIDTH=60)
