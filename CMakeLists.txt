cmake_minimum_required(VERSION 3.16)
project(system76_power_kde
        DESCRIPTION "A plasmoid to control system76 power profile."
        HOMEPAGE_URL "https://github.com/yuri6037/KDE-System76-Power"
        VERSION 1.0.0)

find_package(ECM REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${ECM_MODULE_PATH})

set (QT_MAJOR_VERSION 6)

include(GenerateExportHeader)
include(KDEInstallDirs)
include(KDECMakeSettings)

find_package(Qt6
             CONFIG REQUIRED COMPONENTS
             Core
             DBus
             Quick)

find_package(KF6 ${KF6_REQUIRED_VERSION} REQUIRED COMPONENTS)
find_package(Plasma 6.0.0 REQUIRED)

add_subdirectory(plugin)
add_subdirectory(plasmoid)
