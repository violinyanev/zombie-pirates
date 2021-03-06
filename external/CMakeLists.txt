#  -------------------------------------------------------------------------
#  Copyright (C) 2019 BMW Car IT GmbH
#  All rights reserved.
#  -------------------------------------------------------------------------
#  This document contains proprietary information belonging to BMW Car IT.
#  Passing on and copying of this document, use and communication of its
#  contents is not permitted without prior written authorization.
#  -------------------------------------------------------------------------

set(ramses-sdk_BUILD_EXAMPLES                   OFF CACHE BOOL "Build Example targets: ON, OFF")
###################################################################################
# RAMSES
###################################################################################

# Enable/disable renderer
set(RND_WINDOWS OFF)
set(RND_LINUX   OFF)
set(RND_ANDROID OFF)
set(RND_GENERIC OFF)

if(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
    set(RND_WINDOWS ON)
    set(RND_GENERIC ON)
endif()

if(${CMAKE_SYSTEM_NAME} MATCHES "Linux")
    set(RND_LINUX ON)
    set(RND_GENERIC ON)
endif()

if(${CMAKE_SYSTEM_NAME} MATCHES "Android")
    set(RND_ANDROID ON)
    set(RND_GENERIC ON)
endif()

set(ramses-sdk_ENABLE_TCP_SUPPORT               OFF CACHE BOOL "")

set(ramses-sdk_BUILD_TESTS                      OFF CACHE BOOL "")
set(ramses-sdk_BUILD_DEMOS                      OFF CACHE BOOL "")
set(ramses-sdk_BUILD_SMOKE_TESTS                OFF CACHE BOOL "")
set(ramses-sdk_ENABLE_DLT                       OFF CACHE BOOL "")
set(ramses-sdk_FORCE_OFF_SOMEIP_HU              ON  CACHE BOOL "")
set(ramses-sdk_FORCE_OFF_SOMEIP_IC              ON  CACHE BOOL "")
set(ramses-sdk_integration                      OFF CACHE BOOL "")

set(ramses-sdk_renderer_ramses-renderer-main    OFF CACHE BOOL "")
set(ramses-sdk_ramses-shared-lib                OFF CACHE BOOL "")
set(ramses-sdk_utils                            OFF CACHE BOOL "")
set(ramses-sdk_proprietary_utils                OFF CACHE BOOL "")
set(ramses-sdk_demo                             OFF CACHE BOOL "")
set(ramses-sdk_proprietary_demo                 OFF CACHE BOOL "")
set(ramses-sdk_ramses-daemon                    OFF CACHE BOOL "")

set(ramses-sdk_renderer_Platform_Device_GL                     ${RND_GENERIC} CACHE STRING "")
set(ramses-sdk_ramses-renderer-lib                             ${RND_GENERIC} CACHE STRING "")
set(ramses-sdk_renderer_RendererLib                            ${RND_GENERIC} CACHE STRING "")

set(ramses-sdk_renderer_Platform_Context_WGL                   ${RND_WINDOWS} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Context_WGL                   ${RND_WINDOWS} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Platform_Windows_WGL_4_2_core ${RND_WINDOWS} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Surface_Windows_WGL           ${RND_WINDOWS} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_Windows                ${RND_WINDOWS} CACHE STRING "")

IF ( ${RND_LINUX} OR  ${RND_ANDROID})
set(ramses-sdk_renderer_Platform_Context_EGL                   ON CACHE STRING "")
ENDIF()
set(ramses-sdk_renderer_Platform_Platform_X11_EGL_ES_3_0       ${RND_LINUX} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Surface_X11_EGL               ${RND_LINUX} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_X11                    ${RND_LINUX} CACHE STRING "")

set(ramses-sdk_renderer_Platform_Platform_Android_EGL_ES_3_0       ${RND_ANDROID} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Surface_Android_EGL               ${RND_ANDROID} CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_Android                    ${RND_ANDROID} CACHE STRING "")

set(ramses-sdk_renderer_Platform_WaylandUtilities                          OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_SystemCompositorController_Wayland_IVI    OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_WindowEventsPollingManager_Wayland        OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_TextureUploadingAdapter_Wayland           OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_EmbeddedCompositor_Wayland                OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Logger_Wayland                            OFF CACHE STRING "")
set(ramses-sdk_renderer_DisplayManager                                     OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_Wayland                            OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_Wayland_IVI                        OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Window_Wayland_Shell                      OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Platform_Windows_WGL_4_5                  OFF CACHE STRING "")
set(ramses-sdk_renderer_Platform_Platform_Windows_WGL_ES_3_0               OFF CACHE STRING "")

add_subdirectory(ramses-sdk)
