
set(SPLITE_SOURCES
    mbrcache.c
    spatialite.c
    spatialite_init.c
    pause.c
    metatables.c
    statistics.c
    extra_tables.c
    se_helpers.c
    srid_aux.c
    table_cloner.c
    dbobj_scopes.c
    virtualdbf.c
    virtualXL.c
    virtualfdo.c
    virtualgpkg.c
    virtualbbox.c
    virtualspatialindex.c
    virtualnetwork.c
    virtualrouting.c
    virtualshape.c
    virtualxpath.c
    virtualelementary.c
    virtualknn.c
    virtualknn2.c
    create_routing.c
    virtualgeojson.c
)

add_library(libsplite STATIC ${SPLITE_SOURCES})
target_link_libraries(libsplite PRIVATE libSpatialiteHeader)