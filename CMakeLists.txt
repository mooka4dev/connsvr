
CMAKE_MINIMUM_REQUIRED( VERSION 2.6 )

PROJECT(connsvr)

MESSAGE("===== connsvr begin =====")

# 使用相对路径
SET(CMAKE_USE_RELATIVE_PATHS ON)

# 生成文件列表
FILE(GLOB_RECURSE C_FILE_LIST *.c)
FILE(GLOB_RECURSE CPP_FILE_LIST *.cpp)
FILE(GLOB_RECURSE CC_FILE_LIST *.cc)
SET(ALL_FILE_LIST ${C_FILE_LIST} ${CPP_FILE_LIST} ${CC_FILE_LIST})

# 设定编译选项
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O2 -Wall")

# 包含的头文件目录
INCLUDE_DIRECTORIES(../libmooka)

# 库文件路径
LINK_DIRECTORIES(../../deps/libs)

# 生成可执行文件
ADD_EXECUTABLE(connsvr ${ALL_FILE_LIST})

# 指定需要链接的库文件
TARGET_LINK_LIBRARIES(connsvr mooka)

MESSAGE("===== connsvr end =====")

