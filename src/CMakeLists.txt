
message(STATUS "CMAKE_SOURCE_DIR: ${CMAKE_SOURCE_DIR}")
message(STATUS "PROJECT_BINARY_DIR: ${PROJECT_BINARY_DIR}")

add_executable(opencfd-ec
                    sub_modules.f90
                    opencfd_ec3d_v1.16a.f90
                    sub_interfaces.f90
                    sub_init.f90
                    sub_Residual.f90
                    sub_flux_split.f90
                    sub_boundary.f90
                    sub_turbulence_BL.f90
                    sub_turbulence_SA.f90
                    sub_turbulence_NewSA.f90
                    sub_turbulence_SST.f90
                    sub_time_advance.f90
                    sub_update_buffer_mpi.f90
                    sub_Post.f90
                    sub_time_acceleraction.f90
                    sub_LU_SGS.f90
                    sub_IO.f90  sub_geometry.f90
                    sub_partation_mpi.f90
                    sub_convert_inp.f90
                    sub_read_parameter.f90
                    sub_scheme.f90
                    sub_comput_dw.f90
                    sub_debug.f90
                    sub_filtering.f90
                    sub_boundary_user.f90
                    sub_udate_Meshlink_mpi.f90
                    sub_Finite_Difference1.f90
                    sub_Finite_Difference2.f90
                    sub_Post_timeAverage.f90
                    sub_limitflow.f90)

target_link_libraries(opencfd-ec)
if (MPI_FOUND)
  target_link_libraries(opencfd-ec PRIVATE MPI::MPI_Fortran)
endif (MPI_FOUND)

install(TARGETS opencfd-ec
        RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
        LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
        ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
)
