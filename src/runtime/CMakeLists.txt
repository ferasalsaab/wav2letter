cmake_minimum_required(VERSION 3.5.1)

add_library(
  runtime
  INTERFACE
  )

target_sources(
  runtime
  INTERFACE
  ${CMAKE_CURRENT_SOURCE_DIR}/Logger.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/Serial.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/SpeechStatMeter.cpp
  ${CMAKE_CURRENT_SOURCE_DIR}/Distributed.cpp
  )

target_link_libraries(
  runtime
  INTERFACE
  common
  flashlight::flashlight
  ${GLOG_LIBRARIES}
  ${cereal_LIBRARIES}
  )

target_include_directories(
  runtime
  INTERFACE
  ${GLOG_INCLUDE_DIRS}
  ${cereal_INCLUDE_DIRS}
  )
