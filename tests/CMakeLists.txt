add_executable(test_nnls_cpu main.cpp)
target_link_libraries(test_nnls_cpu io nnls_cpu ${ROOT_LIBRARIES})

add_executable(test_nnls_gpu test_gpu_main.cpp)
target_link_libraries(test_nnls_gpu io nnls_gpu nnls_cpu ${ROOT_LIBRARIES})

add_executable(test_io test_io.cpp)
target_link_libraries(test_io io ${ROOT_LIBRARIES})
