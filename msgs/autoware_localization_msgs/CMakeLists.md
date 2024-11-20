# CMakeLists.txt 解析

这是 `autoware_localization_msgs` 包的 `CMakeLists.txt` 文件，用于定义构建系统并生成所需的消息类型。

## 解释

- **`cmake_minimum_required(VERSION 3.5)`**: 定义了此项目所需的最低 CMake 版本为 3.5。
- **`project(autoware_localization_msgs)`**: 设置项目名称为 `autoware_localization_msgs`。
- **`find_package(ament_cmake_auto REQUIRED)`**: 查找并配置 `ament_cmake_auto` 包，这是一种 ROS 2 的构建工具，它简化了构建过程。
- **`ament_auto_find_build_dependencies()`**: 自动查找并配置构建过程中需要的所有依赖项。
- **`set(msg_files "msg/KinematicState.msg")`**: 定义要生成的消息文件列表，在此例中是 `msg/KinematicState.msg`。
- **`set(msg_dependencies std_msgs geometry_msgs)`**: 指定生成消息所依赖的 ROS2 包，`std_msgs` 和 `geometry_msgs`。
- **`rosidl_generate_interfaces(${PROJECT_NAME} ${msg_files} DEPENDENCIES ${msg_dependencies} ADD_LINTER_TESTS)`**:
  - 使用 `rosidl_generate_interfaces` 来生成 ROS2 消息类型。
  - `${PROJECT_NAME}` 表示项目名称。
  - `${msg_files}` 包含要生成的消息文件。
  - `${msg_dependencies}` 列出了这些消息文件所依赖的其他消息包。
  - `ADD_LINTER_TESTS` 表示如果启用了风格检查，会自动添加代码风格检查。
- **`if(BUILD_TESTING)`**:
  - 如果开启了构建测试，配置 `ament_lint_auto` 来自动查找测试依赖。
  - `ament_lint_auto_find_test_dependencies()` 查找并配置必要的测试依赖包。
- **`ament_auto_package()`**: 生成包并进行安装。



## 代码

```cmake
cmake_minimum_required(VERSION 3.5)  # 设置 CMake 的最低版本要求

# 设置项目名称
project(autoware_localization_msgs)

# 查找并配置 ament_cmake_auto 包
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()  # 自动查找和配置所需的构建依赖

# 设置消息文件
set(msg_files
  "msg/KinematicState.msg")  # 定义要生成的消息文件，此处为 KinematicState.msg

# 设置消息的依赖
set(msg_dependencies
  std_msgs  # 依赖 std_msgs 包
  geometry_msgs)  # 依赖 geometry_msgs 包

# 使用 rosidl_generate_interfaces 来生成 ROS2 消息类型
rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}  # 指定要生成的消息文件
  DEPENDENCIES ${msg_dependencies}  # 指定生成消息所依赖的包
  ADD_LINTER_TESTS)  # 添加代码风格检查（如果需要）

# 如果开启了测试功能，查找并配置 ament_lint_auto 包
if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)  # 查找 ament_lint_auto 包
  ament_lint_auto_find_test_dependencies()  # 查找并配置测试依赖
endif()

# 创建并安装包
ament_auto_package()
```

