cmake_minimum_required (VERSION 2.8)
project (demo)

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MT")

message (STATUS "paramkit_dir='${PARAMKIT_DIR}'")
message (STATUS "paramkit_lib='${PARAMKIT_LIB}'")

include_directories ( ${PARAMKIT_DIR}/include )

set (srcs
	main.cpp
)

set (hdrs
)

add_executable ( ${PROJECT_NAME} ${hdrs} ${srcs} )
target_link_libraries ( ${PROJECT_NAME} ${PARAMKIT_LIB} )
add_dependencies( ${PROJECT_NAME} paramkit )
