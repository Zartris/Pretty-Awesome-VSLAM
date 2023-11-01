# Standard CMake header
cmake_minimum_required(VERSION 3.0.0)
project(Pretty-Awesome-VSLAM VERSION 0.1.0 LANGUAGES C CXX)

# Find packages
# find_package(Eigen3 3.1.0 REQUIRED)
# find_package(Pangolin REQUIRED)


# Include directories
include_directories(
    ${PROJECT_SOURCE_DIR}
    ${PROJECT_SOURCE_DIR}/include
)


# add all source files
# Add all source files in the current src directory to the SOURCES variable
file(GLOB SOURCES "src/*.cpp")
add_library(${PROJECT_NAME} SHARED
    ${SOURCES}
)

# target_link_libraries(${PROJECT_NAME}
#     # ${OpenCV_LIBS}
#     # ${EIGEN3_LIBS}
#     # ${Pangolin_LIBRARIES}
#     # ${PROJECT_SOURCE_DIR}/Thirdparty/DBoW2/lib/libDBoW2.so
#     # ${PROJECT_SOURCE_DIR}/Thirdparty/g2o/lib/libg2o.so
# )

add_executable(MyVSLAM main.cpp ${SOURCES})

# Link libraries
target_link_libraries(MyVSLAM ${PROJECT_NAME})