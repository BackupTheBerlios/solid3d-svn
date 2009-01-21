add_subdirectory(dynamics)
INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/include)


set(sample_SOURCES sample.cpp)
set(gldemo_SOURCES gldemo.cpp)
set(physics_SOURCES physics.cpp)
set(mnm_SOURCES mnm.cpp)

find_package(OpenGL)
find_package(GLUT)
if(OPENGL_FOUND AND OPENGL_GLU_FOUND AND GLUT_FOUND)
  INCLUDE_DIRECTORIES(${GLUT_INCLUDE_DIR})
  INCLUDE_DIRECTORIES(${OPENGL_INCLUDE_DIR})
  set(GLLIBS ${OPENGL_LIBRARIES} ${GLUT_LIBRARIES})

  add_executable(gldemo ${gldemo_SOURCES})
  target_link_libraries (gldemo  ${GLLIBS} solid3d_shared dynamics)

  add_executable(physics ${physics_SOURCES})
  target_link_libraries (physics ${GLLIBS} solid3d_shared dynamics)

  add_executable(mnm ${mnm_SOURCES})
  target_link_libraries (mnm  ${GLLIBS} solid3d_shared dynamics)
endif(OPENGL_FOUND AND OPENGL_GLU_FOUND AND GLUT_FOUND)

add_executable(sample ${sample_SOURCES})
target_link_libraries (sample solid3d_shared)

