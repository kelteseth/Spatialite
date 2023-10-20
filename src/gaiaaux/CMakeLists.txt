
set(GAIAAUX_COMMON_SOURCES gg_sqlaux.c gg_utf8.c)

add_library(libgaiaaux STATIC ${GAIAAUX_COMMON_SOURCES})
target_link_libraries(libgaiaaux PRIVATE libSpatialiteHeader)