message ("Kernels build.")

file(GLOB_RECURSE KERNELS_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/*.cpp")

if ("${CUDA_ENABLED}")
  cuda_add_library (Kernels ${KERNELS_SOURCES})
else ()
  add_library (Kernels ${KERNELS_SOURCES})
endif ()
