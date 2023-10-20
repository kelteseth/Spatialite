
set(DXF_COMMON_SOURCES dxf_parser.c dxf_loader.c dxf_load_distinct.c dxf_load_mixed.c dxf_writer.c)

add_library(libdxf STATIC ${DXF_COMMON_SOURCES})
target_include_directories(libdxf PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
target_link_libraries(libdxf PRIVATE libSpatialiteHeader)