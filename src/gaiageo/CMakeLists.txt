
set(GAIAGEO_COMMON_SOURCES
    gg_advanced.c
    gg_endian.c
    gg_geodesic.c
    gg_geometries.c
    gg_geoscvt.c
    gg_relations.c
    gg_relations_ext.c
    gg_rttopo.c
    gg_extras.c
    gg_shape.c
    gg_transform.c
    gg_wkb.c
    gg_wkt.c
    gg_vanuatu.c
    gg_ewkt.c
    gg_geoJSON.c
    gg_kml.c
    gg_gml.c
    gg_voronoj.c
    gg_xml.c
    gg_matrix.c
)

add_library(libgaiageo STATIC ${GAIAGEO_COMMON_SOURCES})

# Does not exist on Windows
if(WIN32)
    target_compile_definitions(libgaiageo PUBLIC YY_NO_UNISTD_H)
endif()

target_link_libraries(libgaiageo PRIVATE libSpatialiteHeader)