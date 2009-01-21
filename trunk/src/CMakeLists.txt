add_subdirectory(broad)
add_subdirectory(convex)
add_subdirectory(complex)

set(DEPS convex complex broad)
if(USE_INTERNAL_QHULL)
 add_subdirectory(qhull)
 set(DEPS ${DEPS} qhull)
else(USE_INTERNAL_QHULL)
 include_directories(${QHULL_INCLUDE_DIRS})
 set(DEPS ${DEPS} ${QHULL_LIBRARIES})
endif(USE_INTERNAL_QHULL)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_SOURCE_DIR}/src/broad)
include_directories(${CMAKE_SOURCE_DIR}/src/convex)
include_directories(${CMAKE_SOURCE_DIR}/src/complex)

set(SRC_FILES DT_C-api.cpp 
        DT_Object.cpp 
        DT_Scene.cpp 
        DT_Encounter.cpp 
        DT_RespTable.cpp)

set(HDR_FILES DT_AlgoTable.h
	DT_Encounter.h 
	DT_Object.h 
	DT_Scene.h 
	DT_Response.h)

add_library (solid3d_static STATIC ${SRC_FILES} ${HDR_FILES} )
target_link_libraries(solid3d_static ${DEPS})
set_target_properties( solid3d_static PROPERTIES
  OUTPUT_NAME solid3d )


add_library (solid3d_shared SHARED ${SRC_FILES} ${HDR_FILES} )
target_link_libraries(solid3d_shared ${DEPS})
set_target_properties( solid3d_shared PROPERTIES
  SOVERSION "${SOLID_MAJOR}.${SOLID_MINOR}"
  VERSION "${SOLID_MAJOR}.${SOLID_MINOR}.${SOLID_PATCH}"
  OUTPUT_NAME solid3d )


#AM_CPPFLAGS = -I$(top_srcdir)/include -I$(top_srcdir)/src/convex -I$(top_srcdir)/src/complex @DOUBLES_FLAG@ @TRACER_FLAG@

