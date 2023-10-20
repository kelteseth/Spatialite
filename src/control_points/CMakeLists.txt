
set(LIBCONTROL_POINTS_SOURCES gaia_control_points.c grass_crs3d.c grass_georef.c grass_georef_tps.c)
set(CONTROL_POINTS_SOURCES gaia_control_points.c grass_crs3d.c grass_georef.c grass_georef_tps.c)

add_library(libcontrol_points STATIC ${LIBCONTROL_POINTS_SOURCES})
target_link_libraries(libcontrol_points PRIVATE libSpatialiteHeader)