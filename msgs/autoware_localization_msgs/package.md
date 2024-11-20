# Autoware Localization Messages Package

## package.xml 结构

该 `package.xml` 文件是 `autoware_localization_msgs` 包的描述文件，包含包的基本信息、依赖项、构建工具和维护者信息等。

## 解释

- **包名称 (`name`)**：指定包的名称为 `autoware_localization_msgs`，该包包含与本地化相关的消息定义。
- **版本 (`version`)**：版本号为 `1.2.0`，标明该包的版本。
- **描述 (`description`)**：包的简要描述，表明它是 `Autoware` 中与本地化相关的消息包。
- **维护者 (`maintainer`)**：列出包的维护者及其联系方式，便于在包出现问题时进行联系。
- **许可证 (`license`)**：使用 Apache License 2.0 开源协议。
- **构建工具依赖 (`buildtool_depend`)**：
  - `ament_cmake_auto`：表示使用 `ament_cmake` 自动化构建工具进行构建。
  - `rosidl_default_generators`：是 ROS 接口生成器，允许将 `.msg` 文件转换为 C++ 或 Python 的消息类型。
- **依赖 (`depend`)**：
  - `geometry_msgs`：依赖于 `geometry_msgs` 包，通常包含与几何形状、位置、姿态相关的消息类型。
  - `std_msgs`：依赖于标准消息包，提供标准类型，如字符串、布尔值、整数等。
- **执行时依赖 (`exec_depend`)**：
  - `rosidl_default_runtime`：提供消息和服务的运行时支持。
- **测试依赖 (`test_depend`)**：
  - `ament_lint_auto` 和 `ament_lint_common`：提供自动化的代码风格检查和测试工具支持。
- **成员组 (`member_of_group`)**：指定该包属于 `rosidl_interface_packages` 组，表示它提供了 ROS 接口相关的功能。
- **导出设置 (`export`)**：指示该包使用 `ament_cmake` 作为构建系统的类型。

```xml
<?xml version="1.0"?>
<?xml-model href="http://download.ros.org/schema/package_format3.xsd" schematypens="http://www.w3.org/2001/XMLSchema"?>
<package format="3">
  <name>autoware_localization_msgs</name> <!-- 包名 -->
  <version>1.2.0</version> <!-- 包版本 -->
  <description>Autoware localization messages package.</description> <!-- 包描述 -->

  <!-- 维护者信息 -->
  <maintainer email="mfc@leodrive.ai">M. Fatih Cırıt</maintainer>
  <maintainer email="yutaka.kondo@tier4.jp">Yutaka Kondo</maintainer>

  <license>Apache License 2.0</license> <!-- 开源协议 -->

  <!-- 构建工具依赖 -->
  <buildtool_depend>ament_cmake_auto</buildtool_depend> <!-- 自动CMake构建工具 -->
  <buildtool_depend>rosidl_default_generators</buildtool_depend> <!-- 默认ROS接口生成器 -->

  <!-- 包的依赖 -->
  <depend>geometry_msgs</depend> <!-- 与几何消息相关的依赖 -->
  <depend>std_msgs</depend> <!-- 标准消息依赖 -->

  <!-- 执行时的依赖 -->
  <exec_depend>rosidl_default_runtime</exec_depend> <!-- ROSIDL运行时依赖 -->

  <!-- 测试依赖 -->
  <test_depend>ament_lint_auto</test_depend> <!-- 自动化测试依赖 -->
  <test_depend>ament_lint_common</test_depend> <!-- 公共测试工具依赖 -->

  <!-- 包所属的组 -->
  <member_of_group>rosidl_interface_packages</member_of_group>

  <!-- 构建类型 -->
  <export>
    <build_type>ament_cmake</build_type> <!-- 使用ament_cmake进行构建 -->
  </export>
</package>
```



