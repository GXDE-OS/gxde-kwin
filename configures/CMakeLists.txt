option(USE_KWIN_NO_SCALE "use deepin LD_PRELOAD kwin_no_scale" OFF)

install(
    FILES
    kglobalshortcutsrc
    deepin-kwinrc
    deepin-kwinrulesrc
    kdeglobals
    DESTINATION
    "/etc/xdg"
)

install(
    FILES
    org.kde.kwin.compositing.json
    org.kde.kwin.logging.json
    org.kde.kwin.multitaskview.display.json
    org.deepin.displayjack.watermark.display.json
    org.kde.kwin.eventtracking.json
    org.kde.kwin.virtualterminal.switch.json
    DESTINATION
    "/usr/share/dsg/configs/org.kde.kwin"
)

install(
    FILES
    org.kde.kwin.decoration.titlebar.json
    DESTINATION
    "/usr/share/dsg/configs/org.kde.kwin.decoration"
)

install(
    FILES
    org.deepin.kwin.json
    DESTINATION
    "/usr/share/deepin-log-viewer/deepin-log.conf.d/"
)

