set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(io_ROOT "${SRC_DIR}/io")

find_package(Eigen3 REQUIRED)
include_directories(${EIGEN3_INCLUDE_DIR})

# This is required now, but should be removed later
find_package( OpenCV REQUIRED core highgui)
include_directories( ${OpenCV_INCLUDE_DIRS} )


#############################################
set(io_SRC
    ${io_ROOT}/io.cc)
set(io_INCLUDE
    ${io_ROOT}/io.h 
    ${io_ROOT}/io_ply.h)

# use library target, to make accessible to test routines
add_library(super4pcs_io ${io_SRC} ${io_INCLUDE})
target_link_libraries(super4pcs_io ${OpenCV_LIBS} )


