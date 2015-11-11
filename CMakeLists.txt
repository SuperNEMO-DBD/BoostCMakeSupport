project(BoostCMakeSupport NONE)
if(NOT boost_VERSION)
  message(FATAL_ERROR "No boost_VERSION variable set")
endif()

# Script should handle most of the tasks
configure_file(
  ${PROJECT_SOURCE_DIR}/BoostWriteCMakeImportFiles.cmake.in
  ${PROJECT_BINARY_DIR}/BoostWriteCMakeImportFiles.cmake
  @ONLY
  )
execute_process(
  COMMAND ${CMAKE_COMMAND} -P ${PROJECT_BINARY_DIR}/BoostWriteCMakeImportFiles.cmake
  )

