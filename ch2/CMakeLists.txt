# 声明要求的 cmake 最低版本
cmake_minimum_required(VERSION 2.8)

# 声明一个 cmake 工程
project(HelloSLAM)

#这一句是防止Mac编译的时候报warning
set(CMAKE_MACOSX_RPATH 1)

# 添加一个可执行程序
# 语法： add_executable( 程序名 源代码文件 )
add_executable(helloSLAM helloSLAM.cpp)

# 添加一个静态库
add_library(hello libHelloSLAM.cpp)

# 添加一个共享库
add_library(hello_shared SHARED libHelloSLAM.cpp)

# 使用共享库
add_executable(useHello useHello.cpp)
target_link_libraries(useHello hello_shared)

