cmake_minimum_required (VERSION 3.9)
project (template_vol VERSION 0.1.0 DESCRIPTION "template VOL connector" LANGUAGES C)

enable_testing ()
include (CTest)

# Find HDF5
find_package (HDF5 COMPONENTS C REQUIRED)
link_directories (${HDF5_LIBRARY_DIRS})
include_directories (${HDF5_INCLUDE_DIR})
set (LINK_LIBS ${LINK_LIBS} ${HDF5_C_${LIB_TYPE}_LIBRARY})
#message (DEPRECATION "Link path: ${HDF5_LIBRARY_DIRS}")

# It's really easy to pick up the wrong HDF5 library if you set the path
# wrong. Turn this on for added confirmation that you got it right.
#message (DEPRECATION "Include: ${HDF5_INCLUDE_DIR}")

# Set the template VOL connector name
# Do this here so we can use it in both the src and test files
set (TVC_NAME template_vol_connector)

add_subdirectory (src)
add_subdirectory (test)

