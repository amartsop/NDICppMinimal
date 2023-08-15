cmake_minimum_required( VERSION 3.10 )

project( simulation_setup )

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

#Optimization parameters
set(CMAKE_BUILD_TYPE RELEASE)
set(CMAKE_CXX_FLAGS "-O2")

# Add third party directory
add_subdirectory(./libs/ndicapi)

# Include directories
include_directories(
    ./include
    ./libs/ndicapi
    )

set(ALL_LIBS
    ndicapi
)
  

set(SOURCES)


# target
add_executable(main main.cpp ${SOURCES})

target_include_directories(main PRIVATE ndicapi_INCLUDE_DIRS)

    
target_link_libraries(main ${ALL_LIBS})