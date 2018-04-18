cmake_minimum_required(VERSION 3.5)
project(tensorflow_cc_label_image_example)

set(CMAKE_CXX_STANDARD 14)

set(SOURCE_FILES main.cpp)
add_executable(tensorflow_cc_label_image_example ${SOURCE_FILES})

find_package(TensorflowCC REQUIRED COMPONENTS Shared)
include(FindPkgConfig)
pkg_search_module(OPENCV REQUIRED opencv)

# Link the shared Tensorflow library.
target_link_libraries(tensorflow_cc_label_image_example TensorflowCC::Shared)
target_link_libraries(tensorflow_cc_label_image_example ${OPENCV_LIBRARIES})

# For shared library setting, you may also link cuda if it is available.
find_package(CUDA)
message("CUDA_FOUND = ${CUDA_FOUND}")
if(CUDA_FOUND)
    target_link_libraries(example ${CUDA_LIBRARIES})
endif()