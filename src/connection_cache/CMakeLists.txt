
set(LIBCONNECTION_CACHE_SOURCES alloc_cache.c gg_sequence.c)
set(CONNECTION_CACHE_SOURCES alloc_cache.c gg_sequence.c)

add_library(libconnection_cache STATIC ${LIBCONNECTION_CACHE_SOURCES})
target_link_libraries(libconnection_cache PRIVATE libSpatialiteHeader)