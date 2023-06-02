cmake_minimum_required(VERSION 2.8)

project( Hello_SLAM)
# 使用 add_executable(程序名 源代码文件) 添加可执行文件

# add_executable(helloSLAM hello_word.cpp)
# add_library(hello Lib_hello_slam.cpp)   # 会生成 libhello.a 文件，得到的库文件
# # 链接库分为 .a 静态库  和  .so  共享库  share
# add_library(hello_share SHARED Lib_hello_slam.cpp)
# # 编写CMakeLists.txt文件，使用cmake命令对程序进行编译，自动生成Makefile文件，再使用make命令对Makefile文件进行编译

# # 新建build文件夹，使用cmake .. 对上一级文件进行编译，所生成的编译中间文件都会放在build文件夹中，与源代码分开。

# add_executable(hell_print use_hello.cpp)
# target_link_libraries(usehello hello_share)
add_executable(use_hello use_hello.cpp)   # 现在生成了可执行文件
add_library(hell Lib_hello_slam.cpp)   # 添加静态库, 该静态库是前面可执行文件中包含的库文件
target_link_libraries(use_hello hell) # 将文件链接到可执行文件上
