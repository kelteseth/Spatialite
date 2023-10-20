
set(GAIAEXIF_SOURCES gaia_exif.c)

add_library(libgaiaexif STATIC ${GAIAEXIF_SOURCES})
target_link_libraries(libgaiaexif PUBLIC libSpatialiteHeader)