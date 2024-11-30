#add_subdirectory(kwin-xcb)
#add_subdirectory(kdecoration)

message(STATUS "Arch: ${CMAKE_SYSTEM_PROCESSOR}")
if((NOT "${CMAKE_SYSTEM_PROCESSOR}" EQUAL "loongarch64") AND (NOT "${CMAKE_SYSTEM_PROCESSOR}" EQUAL "riscv64"))
    # loong64 和 riscv64 暂不开启该选项
    option(ENABLE_KDECORATION "enable deepin kdecoration plugin" ON)
    add_subdirectory(kdecoration)
endif()

#if (ENABLE_KDECORATION)

    #endif()
