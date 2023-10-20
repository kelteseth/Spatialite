
set(VIRTUALTEXT_SOURCES virtualtext.c)

add_library(libvirtualtext STATIC ${VIRTUALTEXT_SOURCES})
target_link_libraries(libvirtualtext PRIVATE libSpatialiteHeader)