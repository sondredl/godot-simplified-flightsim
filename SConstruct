#!/usr/bin/env python
import os
import sys
import platform

# env = SConscript("SConstruct")
# platform_name = ARGUMENTS.get("platform", "linux")
# env = Environment(CPPPATH=["src/"])
# env.Append(CPPPATH=["src/"])
env = Environment(CPPPATH=[
    "godot-cpp/gen/include/godot-cpp/classes",
    "godot-cpp/gen/include",
    "godot-cpp/gdextension",
    "godot-cpp/gen",
    "godot-cpp/include",
    "godot-cpp/include/core",
    "godot-cpp/include/classes",
    "godot-cpp/include/gen"
],
    CPPDEFINES=["GDEXTENSION_LIBRARY"],
    CXXFLAGS=["-std=c++17"],
)

# For reference:
# - CCFLAGS are compilation flags shared between C and C++
# - CFLAGS are for C-specific compilation flags
# - CXXFLAGS are for C++-specific compilation flags
# - CPPFLAGS are for pre-processor flags
# - CPPDEFINES are for pre-processor defines
# - LINKFLAGS are for linking flags

# tweak this if you want to use different folders, or more folders, to store your source code in.
env.Append(CPPPATH=["src/"])
sources = Glob("src/*.cpp")

# if env["platform"] == "macos":
#     library = env.SharedLibrary(
#         "demo/bin/libgodot-cpp.{}.{}.framework/libgodot-cpp.{}.{}".format(
#             env["platform"], env["target"], env["platform"], env["target"]
#         ),
#         source=sources,
#     )
# else:
library = env.SharedLibrary(
    "bin/libgodot-cpp{}{}".format("", env["SHLIBSUFFIX"]),
    source=sources,
)

Default(library)
