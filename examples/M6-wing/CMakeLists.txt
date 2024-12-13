install(DIRECTORY DESTINATION ${CMAKE_INSTALL_PREFIX}/examples/M6-wing)

# If testing active add test for M6-wing case
if (${BUILD_TESTING})
  set(case_dir "${test_dir}/M6-wing")
  file(MAKE_DIRECTORY ${case_dir})
  file(COPY control.ec DESTINATION ${case_dir})
  file(COPY bc3d.inp DESTINATION ${case_dir})
  file(COPY Mesh3d.dat DESTINATION ${case_dir})
endif()
