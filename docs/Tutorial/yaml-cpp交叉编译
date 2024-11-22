1.下载https://github.com/jbeder/yaml-cpp/archive/refs/tags/yaml-cpp-0.6.0.zip，解压
2.创建toolchain.cmake，内容：

# 指定目标系统
set(CMAKE_SYSTEM_NAME Linux)
# 指定目标平台
#set(CMAKE_SYSTEM_PROCESSOR arm)

# 指定安装目录
set(CMAKE_INSTALL_PREFIX /home/xxx/)

# 指定交叉编译工具链的根路径
set(CROSS_CHAIN_PATH /home/xxx/tool)
set(CMAKE_C_COMPILER ${CROSS_CHAIN_PATH}/bin/linux-gnu-gcc)
set(CMAKE_CXX_COMPILER ${CROSS_CHAIN_PATH}/bin/linux-gnu-g++)

3.修改CMakeLists.txt文件，注释以下内容，加快编译速度
#enable_testing()

#option(YAML_CPP_BUILD_TESTS "Enable testing" ON)
#option(YAML_CPP_BUILD_TOOLS "Enable parse tools" ON)
#option(YAML_CPP_BUILD_CONTRIB "Enable contrib stuff in library" ON)

4.编译
mkdir build
cd build
cmake ..
sudo make
sudo make install

5.安装目录下生成头文件和库文件

6.使用
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/xxx)
target_link_libraries(${PROJECT_NAME} PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/xxx/yaml-cpp/libyaml-cpp.a)

#include <yaml-cpp/yaml.h>

YAML::Node fconfig = YAML::LoadFile("/config/Cfg.yaml");
double fcfg_th = fconfig["th"].as<double>();

