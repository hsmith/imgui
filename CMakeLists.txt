###############################################################################
#
# IMGUI
#
# Howard N Smith (howard@blacktriangles.com)
# November 27, 2015
# (c) blacktriangles 2015 (http://www.blacktriangles.com)
###############################################################################

set( IMGUI_INCLUDE_DIR
      "${CMAKE_CURRENT_LIST_DIR}"
      "${CMAKE_CURRENT_LIST_DIR}/examples/libs/gl3w"
      CACHE STRING "dear imgui, include directory"
  )

include_directories( ${IMGUI_INCLUDE_DIR} )

### gl3w ######################################################################
add_library(
    gl3w
      "examples/libs/gl3w/GL/gl3w.c"
  )

target_link_libraries(
    gl3w
    PUBLIC
      GL
  )

### imgui library #############################################################
add_library(
    imgui
      "imgui.cpp"
      "imgui_demo.cpp"
      "imgui_draw.cpp"
  )

target_link_libraries(
    imgui
    PUBLIC
      dl
      GL
      gl3w
  )
