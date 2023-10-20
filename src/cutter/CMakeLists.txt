
set(LIBCUTTER_SOURCES gaia_cutter.c)
set(CUTTER_SOURCES gaia_cutter.c)

add_library(libcutter STATIC ${LIBCUTTER_SOURCES})
target_link_libraries(libcutter PRIVATE libSpatialiteHeader)