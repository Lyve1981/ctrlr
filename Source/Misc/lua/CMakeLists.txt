cmake_minimum_required(VERSION 3.10)
project(lua)

add_library(lua STATIC)

target_sources(lua PRIVATE 
	src/lua.c
	include/lauxlib.h
	include/lua.h
	include/luaconf.h
	include/lualib.h
)

target_include_directories(lua PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/include")
