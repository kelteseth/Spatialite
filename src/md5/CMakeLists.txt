
set(MD5_SOURCES md5.c gaia_md5.c)

add_library(libmd5 STATIC ${MD5_SOURCES})
target_link_libraries(libmd5 PRIVATE libSpatialiteHeader)