CMAKE_MINIMUM_REQUIRED(VERSION 3.0)

SET(PROJECT_NAME "bitcount")
PROJECT("${PROJECT_NAME}")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

FILE(GLOB files
  "*.h"
  "*.cpp"
)
FILE(GLOB hidden
	".*"
)
FILE(GLOB resources
  "*.*"
)

ADD_EXECUTABLE(${PROJECT_NAME} ${files})

LIST(REMOVE_ITEM resources ${files} ${hidden} "${CMAKE_SOURCE_DIR}/CMakeLists.txt")
FILE(COPY ${resources} DESTINATION "Debug")
FILE(COPY ${resources} DESTINATION "Release")
