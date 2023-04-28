cmake_minimum_required(VERSION 3.15)

project(ui_app CXX)

# Add executable
add_executable (${PROJECT_NAME} "")

target_sources(
    ${PROJECT_NAME} 
    PRIVATE
      main.cpp
)

install(
    TARGETS ${PROJECT_NAME}
    EXPORT ${PROJECT_NAME}Targets
    ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR}
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR}
    RUNTIME DESTINATION ${CMAKE_INSTALL_BINDIR}
)