set(SPATIALITE_SOURCES
    spatialite_private.h
    spatialite/gaiaconfig.h
    spatialite/gaiaconfig.h.in
    spatialite/gaiaconfig-msvc.h
    spatialite/gaiaconfig-msvc.h.in
    spatialite/gaiaexif.h
    spatialite/gaiaaux.h
    spatialite/gaiamatrix.h
    spatialite/gaiageo.h
    spatialite/gg_const.h
    spatialite/gg_structs.h
    spatialite/gg_core.h
    spatialite/gg_mbr.h
    spatialite/gg_formats.h
    spatialite/gg_dynamic.h
    spatialite/gg_advanced.h
    spatialite/gg_xml.h
    spatialite/gg_wfs.h
    spatialite/gg_dxf.h
    spatialite/spatialite_ext.h
    spatialite/sqlite.h
    spatialite/debug.h
    spatialite/geopackage.h
    spatialite/control_points.h
    spatialite/gaia_topology.h
    spatialite/gaia_network.h
    spatialite/gg_sequence.h
    spatialite/stored_procedures.h
    spatialite/geojson.h
)

find_package(GEOS CONFIG REQUIRED)
find_package(Iconv)
find_package(LibXml2 REQUIRED)
find_package(unofficial-sqlite3 CONFIG REQUIRED)
find_package(ZLIB REQUIRED)
find_package(PROJ CONFIG REQUIRED)

add_library(libSpatialiteHeader INTERFACE ${SPATIALITE_SOURCES})
target_link_libraries(libSpatialiteHeader INTERFACE unofficial::sqlite3::sqlite3 LibXml2::LibXml2 GEOS::geos_c Iconv::Iconv ZLIB::ZLIB PROJ::proj)

target_include_directories(libSpatialiteHeader INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/spatialite
)
