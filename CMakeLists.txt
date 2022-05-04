# CMake 最低版本号要求
cmake_minimum_required(VERSION 3.0.0)
 
# 项目信息
project(test1 VERSION 0.1.0)
 
#设置exe输出目录
set(EXECUTABLE_OUTPUT_PATH "${PROJECT_SOURCE_DIR}/bin")  
 
# 查找当前目录下的所有源文件
# 并将名称保存到 DIR_SRCS 变量
aux_source_directory(. DIR_SRCS)
include_directories (${PROJECT_SOURCE_DIR}/include)
# 指定生成目标
add_executable(Demo ${DIR_SRCS})
#add_executable(${PROJECT_NAME} main.cpp)

link_directories(${PROJECT_SOURCE_DIR}/lib-vc2017)
target_link_libraries(Demo ${PROJECT_SOURCE_DIR}/lib-vc2017/StaticLib_glad.lib ${PROJECT_SOURCE_DIR}/lib-vc2017/glfw3.lib)