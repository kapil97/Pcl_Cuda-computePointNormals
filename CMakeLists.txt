cmake_minimum_required(VERSION 3.5)
project(cuda_normals_test)

find_package(PCL REQUIRED COMPONENTS common io cuda_common cuda_io cuda_features visualization)
find_package(CUDA REQUIRED)
find_package(OpenCV REQUIRED)

add_executable(normals_test src/main.cpp)
target_include_directories(normals_test PRIVATE ${PCL_INCLUDE_DIRS})
target_include_directories(normals_test PRIVATE ${CUDA_INCLUDE_DIRS})
target_include_directories(normals_test PRIVATE ${OpenCV_INCLUDE_DIRS})
target_link_libraries(normals_test ${CUDA_LIBRARIES} ${PCL_LIBRARIES} ${OpenCV_LIBRARIES})