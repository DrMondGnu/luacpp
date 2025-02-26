cmake_minimum_required(VERSION 3.9)
project(LuaCpp)

set(CMAKE_CXX_STANDARD 17)

# Source files
set(SOURCE_FILES
	Lua.hpp
	LuaCpp.hpp
	LuaVersion.cpp LuaVersion.hpp
	Engine/LuaState.cpp Engine/LuaState.hpp
	Engine/LuaType.cpp Engine/LuaType.hpp
	Engine/LuaTNil.cpp Engine/LuaTNil.hpp
	Engine/LuaTString.cpp Engine/LuaTString.hpp
	Engine/LuaTNumber.cpp Engine/LuaTNumber.hpp
	Engine/LuaTBoolean.cpp Engine/LuaTBoolean.hpp
	Engine/LuaTTable.cpp Engine/LuaTTable.hpp
	Engine/LuaTUserData.cpp Engine/LuaTUserData.hpp
	Registry/LuaRegistry.cpp Registry/LuaRegistry.hpp
	Registry/LuaCodeSnippet.cpp Registry/LuaCodeSnippet.hpp
	Registry/LuaCompiler.cpp Registry/LuaCompiler.hpp
	Registry/LuaCFunction.cpp Registry/LuaCFunction.hpp
	Registry/LuaLibrary.cpp Registry/LuaLibrary.hpp
	LuaContext.cpp LuaContext.hpp
	LuaMetaObject.cpp LuaMetaObject.hpp
)

# add_library(luacpp SHARED ${SOURCE_FILES})
add_library(luacpp_static STATIC ${SOURCE_FILES})

set_target_properties(luacpp_static PROPERTIES OUTPUT_NAME luacpp)

target_include_directories(luacpp_static
    INTERFACE .
    )

# target_link_libraries(luacpp PUBLIC lua_static)
target_link_libraries(luacpp_static PUBLIC lua_static)

