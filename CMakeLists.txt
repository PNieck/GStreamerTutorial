cmake_minimum_required(VERSION 3.15.3)
project(GstreamerTutorial)

find_package(PkgConfig REQUIRED)
#pkg_check_modules(gtk3 REQUIRED IMPORTED_TARGET gtk+-3.0)
pkg_search_module(gstreamer REQUIRED IMPORTED_TARGET gstreamer-1.0>=1.4)
# pkg_search_module(gstreamer-sdp REQUIRED IMPORTED_TARGET gstreamer-sdp-1.0>=1.4)
# pkg_search_module(gstreamer-app REQUIRED IMPORTED_TARGET gstreamer-app-1.0>=1.4)
# pkg_search_module(gstreamer-video REQUIRED IMPORTED_TARGET gstreamer-video-1.0>=1.4)

add_executable(HelloWorld HelloWorld.c)
target_link_libraries(HelloWorld
    PkgConfig::gstreamer
)

add_executable(GStreamerConcepts GStreamerConcepts.c)
target_link_libraries(GStreamerConcepts
    PkgConfig::gstreamer
)

add_executable(DynamicPipelines DynamicPipelines.c)
target_link_libraries(DynamicPipelines
    PkgConfig::gstreamer
)

add_executable(TimeManagment TimeManagment.c)
target_link_libraries(TimeManagment
    PkgConfig::gstreamer
)
