
include_directories( ${ENGINE_COMMON_INCLUDES} )


########### next target ###############

set(thrift_LIB_SRCS
    thrift/Thrift.cpp
    thrift/server/TSimpleServer.cpp
    thrift/transport/TSocket.cpp
    thrift/transport/TServerSocket.cpp
    thrift/transport/TBufferTransports.cpp
    thrift/TApplicationException.cpp)

add_definitions(-DTHRIFT_SQUELCH_CONSOLE_OUTPUT)

add_library(thrift SHARED ${thrift_LIB_SRCS})

set_target_properties(thrift PROPERTIES VERSION 1.0.0 SOVERSION 1)

install(TARGETS thrift DESTINATION ${ENGINE_LIBDIR} COMPONENT libs)

