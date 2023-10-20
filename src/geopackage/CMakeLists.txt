set(SHARED_SOURCES
    gpkg_add_tile_triggers.c
    gpkg_get_normal_row.c
    gpkg_get_normal_zoom.c
    gpkgGetImageType.c
    gpkgCreateBaseTables.c
    gpkgInsertEpsgSRID.c
    gpkgCreateTilesTable.c
    gpkgCreateTilesZoomLevel.c
    gpkgAddGeometryColumn.c
    gpkgMakePoint.c
    gpkgBinary.c
    gpkg_add_geometry_triggers.c
    gpkg_add_spatial_index.c
    gaia_cvt_gpkg.c
)

add_library(libgeopackage STATIC ${SHARED_SOURCES})
target_link_libraries(libgeopackage PRIVATE libSpatialiteHeader)