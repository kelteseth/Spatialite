cmake_minimum_required(VERSION 3.23)

# Project name and version
project(libSpatialite VERSION 5.1.0)

# Include directories
# Todo remove me
include_directories(
    ${CMAKE_SOURCE_DIR} # This is the root directory where config-msvc.h resides
)

# Source directories
add_subdirectory(src)

add_library(libSpatialite SHARED
    ${CMAKE_CURRENT_SOURCE_DIR}/src/headers/spatialite.c
    ${CMAKE_CURRENT_SOURCE_DIR}/src/headers/spatialite.h
)
target_compile_definitions(libSpatialite PRIVATE DLL_EXPORT)

option(ENABLE_EXAMPLES "Enable building of examples" OFF)
if(ENABLE_EXAMPLES)
    add_subdirectory(examples)
endif()

option(ENABLE_TESTS "Enable building of tests" OFF)
if(ENABLE_TESTS)
    add_subdirectory(test)
endif()

# pkg-config
find_package(PkgConfig REQUIRED)
configure_file(${CMAKE_SOURCE_DIR}/spatialite.pc.in ${CMAKE_BINARY_DIR}/spatialite.pc @ONLY)
install(FILES ${CMAKE_BINARY_DIR}/spatialite.pc
    DESTINATION ${CMAKE_INSTALL_LIBDIR}/pkgconfig)

# For coverage (you'll need to have lcov installed)
option(BUILD_COVERAGE "Build with coverage support" OFF)

if(BUILD_COVERAGE)
    find_package(LCOV REQUIRED)
    add_custom_target(coverage-init
        COMMAND ${LCOV_EXECUTABLE} --directory src --capture --initial --output-file libspatialite_cov.info
    )
    add_custom_target(coverage
        COMMAND ${LCOV_EXECUTABLE} --rc lcov_branch_coverage=1 --directory src --output-file libspatialite_cov.info --capture
        COMMAND ${LCOV_EXECUTABLE} --rc lcov_branch_coverage=1 --remove libspatialite_cov.info "*/src/gaiageo/*Lexer.l" --output-file libspatialite_cov.info
        COMMAND genhtml --rc lcov_branch_coverage=1 -o covresults libspatialite_cov.info
    )
endif()
