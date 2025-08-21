project(lifelong)

cmake_minimum_required (VERSION 3.11)
set(CMAKE_CXX_STANDARD 11)

include_directories("inc")
file(GLOB SOURCES "src/*.cpp")
file(GLOB HEADERS "inc/*.h")

# Find Boost
find_package( Boost 1.49.0 REQUIRED COMPONENTS program_options system filesystem)
include_directories( ${Boost_INCLUDE_DIRS} )


add_executable(lifelong ${SOURCES} ${HEADERS})
target_link_libraries(lifelong ${Boost_LIBRARIES})
