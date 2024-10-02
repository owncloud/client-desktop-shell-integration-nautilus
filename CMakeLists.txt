cmake_minimum_required(VERSION 3.16)

project(owncloud-client-shell-integration-nautilus)

option(REQUIRE_OWNCLOUD_RESOURCES "We depend on the ownCloud resources, if your distribution does provide alternative icons you can disable this requirement" ON)

include(FeatureSummary)
include(GNUInstallDirs)

if (REQUIRE_OWNCLOUD_RESOURCES)
    find_package(ownCloudShellResources 1.0.0 REQUIRED)
    set_package_properties(ownCloudShellResources PROPERTIES TYPE REQUIRED DESCRIPTION "Required ownCloud resources and icons" URL "https://github.com/owncloud/client-desktop-shell-integration-resources")
endif()

set(APPLICATION_NAME       "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_SHORTNAME  "ownCloud" CACHE STRING "Branding parameter")
set(APPLICATION_EXECUTABLE "owncloud" CACHE STRING "Branding parameter")

add_subdirectory(src)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
