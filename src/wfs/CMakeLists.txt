
set(LIBWFS_SOURCES wfs_in.c)

add_library(libwfs STATIC ${LIBWFS_SOURCES})
target_link_libraries(libwfs PRIVATE libSpatialiteHeader)