set(TARGET_NAME "deepin-chameleon")

add_definitions(-DTARGET_NAME=\\"${TARGET_NAME}\\")

find_package(Qt6 CONFIG REQUIRED COMPONENTS Core)
find_package(KF6CoreAddons REQUIRED)
find_package(KF6Config REQUIRED)
find_package(KDecoration2 REQUIRED)

option(USE_LIB_KWIN_XCB "Use libkwin-xcb" OFF)

set(CMAKE_CXX_STANDARD 17)

add_library(
    ${TARGET_NAME}
    MODULE
    main.cpp
    chameleon.cpp
    chameleontheme.cpp
    chameleonbutton.cpp
    chameleonshadow.cpp
    themes.qrc
)

target_link_libraries(
    ${TARGET_NAME}
    PUBLIC
    Qt6::Core
    PRIVATE
    KDecoration2::KDecoration
    KF6::CoreAddons
    KF6::ConfigCore
)

if (USE_LIB_KWIN_XCB)
    include_directories(../kwin-xcb-kde6/lib)
    target_link_libraries(${TARGET_NAME} kwin-xcb)
else()
    add_definitions(-DDISBLE_DDE_KWIN_XCB)
endif()

install(TARGETS ${TARGET_NAME} DESTINATION ${QT_INSTALL_PLUGINS}/org.kde.kdecoration2)
