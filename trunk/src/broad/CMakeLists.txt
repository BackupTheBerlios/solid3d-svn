set(SRC_FILES BP_C-api.cpp
	BP_EndpointList.cpp
	BP_Proxy.cpp
	BP_Scene.cpp)
set(HDR_FILES  BP_ProxyList.h
	BP_Scene.h
	BP_Endpoint.h  
	BP_EndpointList.h    
	BP_Proxy.h)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

#add_definitions(-D_CRT_SECURE_NO_DEPRECATE)
add_library (broad STATIC ${SRC_FILES} ${HDR_FILES} )


