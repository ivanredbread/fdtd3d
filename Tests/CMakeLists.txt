message ("Source build.")

include_directories ("${PROJECT_SOURCE_DIR}/Source/Helpers")

include_directories ("${PROJECT_SOURCE_DIR}/Source/Physics")

include_directories ("${PROJECT_SOURCE_DIR}/Source/Kernels")
set (LIBS ${LIBS} Kernels)

include_directories ("${PROJECT_SOURCE_DIR}/Source/Settings/")
set (LIBS ${LIBS} Settings)

include_directories ("${PROJECT_SOURCE_DIR}/Source/Coordinate")
set (LIBS ${LIBS} Coordinate)

include_directories ("${PROJECT_SOURCE_DIR}/Source/Grid")
include_directories ("${PROJECT_SOURCE_DIR}/Source/Layout")
include_directories ("${PROJECT_SOURCE_DIR}/Source/File-Management/")
include_directories ("${PROJECT_SOURCE_DIR}/Source/File-Management/Loader")
include_directories ("${PROJECT_SOURCE_DIR}/Source/File-Management/Dumper")

add_executable (unit-test-parallel-grid unit-test-parallel-grid.cpp)
target_link_libraries (unit-test-parallel-grid ${LIBS} Grid Helpers Settings Layout)

add_executable (perf-test-parallel-grid perf-test-parallel-grid.cpp)
target_link_libraries (perf-test-parallel-grid ${LIBS} Grid Helpers Settings Layout)

add_executable (unit-test-grid unit-test-grid.cpp)
target_link_libraries (unit-test-grid ${LIBS} Grid Helpers Settings)

add_executable (unit-test-dumpers-loaders unit-test-dumpers-loaders.cpp)
target_link_libraries (unit-test-dumpers-loaders ${LIBS} Grid Loader Dumper Helpers Settings)

add_executable (unit-test-coordinate unit-test-coordinate.cpp)
target_link_libraries (unit-test-coordinate Helpers Settings Coordinate)

add_executable (unit-test-layout unit-test-layout.cpp)
target_link_libraries (unit-test-layout Helpers Settings Coordinate Layout)
