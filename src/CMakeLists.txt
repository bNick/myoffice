#cmake_minimum_required(VERSION 3.5)
# project(aicup2020)

#set (CMAKE_CXX_STANDARD 14)

# OS and compiler checks.
if(WIN32)
    add_definitions(-DWIN32)
    SET(PROJECT_LIBS Ws2_32.lib)
endif()

file(GLOB HEADERS "*.hpp" "model/*.hpp")
SET_SOURCE_FILES_PROPERTIES(${HEADERS} PROPERTIES HEADER_FILE_ONLY TRUE)
file(GLOB SRC "*.cpp" "model/*.cpp")
add_executable(aicup2020 ${HEADERS} ${SRC})
add_library(aicup2020_lib STATIC ${SRC})
TARGET_LINK_LIBRARIES(aicup2020 ${PROJECT_LIBS})