include_directories(include)

add_library(Worklist SHARED
    Worklist.cpp
)
set_target_properties(Worklist PROPERTIES
    SOVERSION 0
    COMPILE_FLAGS "-g -std=c++14 -fno-rtti"
)

include(GNUInstallDirs)
install(TARGETS Worklist
    LIBRARY DESTINATION ${CMAKE_INSTALL_LIBDIR})
