# CMake_test_template

cmake_minimum_required(VERSION 3.29)
project(Test_Project)

# Latest CXX Standard
set(CMAKE_CXX_STANDARD 23)

### Include Dependencies ###

# Include spdlog
add_subdirectory(.vessel/externals/spdlog)

# Gather all from core
file(GLOB_RECURSE Core Test_Project/Source/Core/*.cpp Test_Project/Source/Core/*.h)

# Executable
add_executable(Test_Project ${Core})

# Link dependencies
target_link_libraries(Test_Project PRIVATE spdlog::spdlog_header_only)


