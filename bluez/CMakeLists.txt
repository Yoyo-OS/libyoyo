set(bluezqtextensionplugin_SRCS
    declarativemanager.cpp
    declarativeadapter.cpp
    # declarativebattery.cpp
    declarativedevice.cpp
    declarativeinput.cpp
    declarativemediaplayer.cpp
    declarativedevicesmodel.cpp
    bluezqtextensionplugin.cpp
    applet/devicesproxymodel.cpp
    applet/bluetoothagent.cpp
    applet/bluetoothmanager.cpp
)

add_library(yoyobluez_qmlplugins SHARED ${bluezqtextensionplugin_SRCS})

find_package(KF5BluezQt REQUIRED)

target_link_libraries(yoyobluez_qmlplugins
    Qt5::Core
    Qt5::Qml
    Qt5::DBus
    KF5::BluezQt
)

install(TARGETS yoyobluez_qmlplugins DESTINATION ${INSTALL_QMLDIR}/Yoyo/Bluez)
install(FILES DevicesModel.qml DESTINATION ${INSTALL_QMLDIR}/Yoyo/Bluez)
install(FILES qmldir DESTINATION ${INSTALL_QMLDIR}/Yoyo/Bluez)
