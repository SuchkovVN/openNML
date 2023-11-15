set(TARGET_NAME opennml_utils)

file(GLOB_RECURSE SOURCES "*.cpp" "*.hpp")

add_library(${TARGET_NAME} STATIC ${SOURCES})
add_library(nml::utils ALIAS ${TARGET_NAME})

target_include_directories(${TARGET_NAME} PUBLIC 
    <BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    <INSTALL_INTERFACE:include>
)
