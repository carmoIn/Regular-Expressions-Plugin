project(regular-expression)

cmake_minimum_required(VERSION 3.2)
list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

include(AMXConfig)
include(AddSAMPPlugin)

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}/includes
	${CMAKE_CURRENT_SOURCE_DIR}/includes/SDK
	${CMAKE_CURRENT_SOURCE_DIR}/includes/onig-5.9.5
)

add_definitions(-DSAMPGDK_AMALGAMATION)

add_samp_plugin(regular-expression
	${CMAKE_CURRENT_SOURCE_DIR}/includes/SDK/amxplugin.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/includes/onig-5.9.5/oniguruma.h
	${CMAKE_CURRENT_SOURCE_DIR}/src/RegEx.cpp
	${CMAKE_CURRENT_SOURCE_DIR}/RegEx.def
)
