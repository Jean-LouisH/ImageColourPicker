# CMakeList.txt : CMake project for Lilliputian, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

file(GLOB_RECURSE image_colour_picker_sources "[a-zA-Z]*.cpp")
file(GLOB_RECURSE image_colour_picker_headers "[a-zA-Z]*.hpp")

add_executable(image_colour_picker
	  ${image_colour_picker_sources}
	  ${image_colour_picker_headers}
)

find_library(SDL2 SDL2.lib SDL2main.lib PATHS ../../thirdparty/SDL2-2.0.12/lib/x64)
find_library(SDL2_Image SDL2_image.lib PATHS ../../thirdparty/SDL2_image-2.0.5/lib/x64)
find_library(SDL2_TTF SDL2_ttf.lib PATHS ../../thirdparty/SDL2_ttf-2.0.15/lib/x64)

include_directories(
		../../thirdparty/SDL2-2.0.12/include
		../../thirdparty/SDL2_image-2.0.5/include
		../../thirdparty/SDL2_ttf-2.0.15/include
)

target_link_libraries (image_colour_picker
		${SDL2}
		${SDL2_Image}
		${SDL2_TTF}
)