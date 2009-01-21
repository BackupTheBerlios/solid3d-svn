set(SRC_FILES DT_Accuracy.cpp  
      DT_Cone.cpp    
      DT_Cylinder.cpp     
      DT_PenDepth.cpp
      DT_Polyhedron.cpp  
      DT_Sphere.cpp    
      DT_TriEdge.cpp
      DT_Box.cpp       
      DT_Convex.cpp  
      DT_LineSegment.cpp  
      DT_Point.cpp
      DT_Polytope.cpp    
      DT_Triangle.cpp)

set(HDR_FILES  DT_Accuracy.h  
      DT_Cone.h      
      DT_GJK.h         
      DT_LineSegment.h  
      DT_Point.h
      DT_Shape.h      
      DT_Triangle.h
      DT_Array.h     
      DT_Convex.h    
      DT_Hull.h        
      DT_Minkowski.h
      DT_Polyhedron.h  
      DT_Sphere.h     
      DT_TriEdge.h
      DT_Box.h       
      DT_Cylinder.h  
      DT_IndexArray.h  
      DT_PenDepth.h
      DT_Polytope.h    
      DT_Transform.h  
      DT_VertexBase.h)


include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

#add_definitions(-D_CRT_SECURE_NO_DEPRECATE)
add_library (convex STATIC ${SRC_FILES} ${HDR_FILES} )


