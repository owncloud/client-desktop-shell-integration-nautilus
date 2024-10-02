cmake_minimum_required(VERSION 3.16)

project(owncloud-client-shell-integration-nautilus)

include(FeatureSummary)
include(GNUInstallDirs)

set(APPLICATION_NAME       "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_SHORTNAME  "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_EXECUTABLE "owncloud" CACHE STRING "Branding parameter")

add_subdirectory(src)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
