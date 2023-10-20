
set(TOPOLOGY_SOURCES
    gaia_topology.c
    gaia_auxtopo.c
    gaia_auxtopo_table.c
    gaia_topostmts.c
    topo_callbacks.c
    lwn_network.c
    lwn_network.h
    lwn_network_private.h
    network_private.h
    gaia_network.c
    gaia_auxnet.c
    gaia_netstmts.c
    net_callbacks.c
)

add_library(libtopology STATIC ${TOPOLOGY_SOURCES})
target_link_libraries(libtopology PRIVATE libSpatialiteHeader)