cmake_minimum_required (VERSION 3.9)

include (../../common.cmake)

project (karabiner_console_user_server)

include_directories(
  ./include
)

add_executable(
  karabiner_console_user_server
  src/main.cpp
  ../../vendor/cget/src/pqrs/osx/frontmost_application_monitor/impl/objc.m
)

set_target_properties(
  karabiner_console_user_server
  PROPERTIES

  XCODE_ATTRIBUTE_ENABLE_HARDENED_RUNTIME
  YES
)

target_link_libraries(
  karabiner_console_user_server
  "-framework Carbon"
  "-framework Cocoa"
  "-framework SystemConfiguration"
)
