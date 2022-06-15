set(SCREEN_SRCS
    draganddrop/declarativedroparea.cpp
    draganddrop/declarativedragdropevent.cpp
    draganddrop/declarativemimedata.cpp
    plugin.cpp
)

find_package(Qt5 COMPONENTS Core DBus Quick LinguistTools REQUIRED)

add_library(yoyodragdrop_qmlplugins SHARED ${SCREEN_SRCS})

target_link_libraries (yoyodragdrop_qmlplugins
    Qt5::Core
    Qt5::Quick
    Qt5::Gui
    Qt5::DBus
)

install(TARGETS yoyodragdrop_qmlplugins DESTINATION ${INSTALL_QMLDIR}/Yoyo/DragDrop)
install(FILES qmldir DESTINATION ${INSTALL_QMLDIR}/Yoyo/DragDrop)