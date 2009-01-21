set(DYNAMICS_SRCS 
	Dynamic.cpp 
	Dynamic.h 
        Kinetic.cpp 
        Kinetic.h 
        RigidBody.cpp 
        RigidBody.h)

INCLUDE_DIRECTORIES(${CMAKE_SOURCE_DIR}/include)

# build sources
add_library(dynamics STATIC ${DYNAMICS_SRCS})

