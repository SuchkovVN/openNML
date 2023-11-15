set(TARGET_NAME opennnml_core)

file(GLOB_RECURSE SOURCES "*.cc" "*.hpp")


add_library(${TARGET_NAME} STATIC ${SOURCES})
add_library(nml::core ALIAS ${TARGET_NAME})

target_include_directories(${TARGET_NAME} PUBLIC 
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>     
)
