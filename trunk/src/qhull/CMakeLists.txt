set(SRC_FILES  geom2.c 
	geom.c  
	global.c  
	io.c  
	mem.c  
	merge.c  
	poly2.c
	poly.c  
	qhull.c
	qset.c  
	stat.c  
	user.c)
set (HDR_FILES  geom.h  
	io.h  
	mem.h  
	merge.h  
	poly.h  
	qhull_a.h  
	qhull.h  
	qset.h  
	stat.h
	user.h)

#add_definitions(-D_CRT_SECURE_NO_DEPRECATE)
add_library (qhull STATIC ${SRC_FILES} ${HDR_FILES} )



