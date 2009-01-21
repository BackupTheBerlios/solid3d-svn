set(SRC_FILES DT_BBoxTree.cpp
	DT_Complex.cpp)

set(HDR_FILES DT_BBoxTree.h
	DT_CBox.h
	DT_Complex.h)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${CMAKE_SOURCE_DIR}/src/convex)
include_directories(${CMAKE_SOURCE_DIR}/src)

#add_definitions(-D_CRT_SECURE_NO_DEPRECATE)
add_library (complex STATIC ${SRC_FILES} ${HDR_FILES} )


