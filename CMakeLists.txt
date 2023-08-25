cmake_minimum_required(VERSION 3.16)

project(owncloud-client-shell-integration-nautilus)

include(FeatureSummary)

set(KF5_MIN_VERSION "5.52.0")

find_package(ECM ${KF5_MIN_VERSION} REQUIRED CONFIG)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR} "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

set_package_properties(DolphinVcs PROPERTIES
    DESCRIPTION "the Dolphin plugin library"
    URL "http://dolphin.kde.org/"
    TYPE REQUIRED
    PURPOSE "Provides plugin interfaces for Dolphin."
)

set(KDE_INSTALL_DIRS_NO_DEPRECATED TRUE)
include(KDEInstallDirs)
# kcoreaddons_add_plugin uses deprecated VAR PLUGIN_INSTALL_DIR
# when that is fixed and you want to remove this workaround,
# you need to _require_ the new enough kcoreaddons
set(PLUGIN_INSTALL_DIR "${KDE_INSTALL_PLUGINDIR}")
include(KDECMakeSettings)
include(KDECompilerSettings)
include(ECMMarkNonGuiExecutable)
include(GenerateExportHeader)

set(APPLICATION_NAME       "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_SHORTNAME  "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_EXECUTABLE "owncloud" CACHE STRING "Branding parameter")

add_subdirectory(src)
