project(ObEngineTests)

file(GLOB_RECURSE OBT_HEADERS src/*.hpp)
file(GLOB_RECURSE OBT_SOURCES src/*.cpp)

add_executable(ObEngineTests ${OBT_HEADERS} ${OBT_SOURCES})

target_include_directories(ObEngineTests
  PRIVATE
    $<BUILD_INTERFACE:${OPENGL_INCLUDE_DIR}>
)

target_link_libraries(ObEngineTests ObEngineCore)
target_link_libraries(ObEngineTests catch)

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD_REQUIRED ON)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_EXTENSIONS OFF)