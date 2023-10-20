
set(SHAPEFILES_SOURCES shapefiles.c validator.c)

add_library(libshapefiles STATIC ${SHAPEFILES_SOURCES})
target_link_libraries(libshapefiles PRIVATE libSpatialiteHeader)
