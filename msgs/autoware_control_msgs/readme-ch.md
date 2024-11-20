# Autoware 控制消息

## 设计

车辆尺寸和轴线信息：[Autoware 设计文档](https://autowarefoundation.github.io/autoware-documentation/main/design/autoware-interfaces/components/vehicle-dimensions/)

### Lateral.msg

定义了一个带有时间戳的横向控制命令消息。

该消息传递了期望车辆横向状态在指定时间点 `control_time` 的配置信息：

- 字段 `steering_tire_angle` 为必填项。
- 字段 `steering_tire_rotation_rate` 是可选项，但某些节点可能需要使用。
  - 如果使用此字段，则必须将 `is_defined_steering_tire_rotation_rate` 设置为 `true`。

### Longitudinal.msg

定义了一个带有时间戳的纵向控制命令消息。

该消息传递了期望车辆纵向状态在指定时间点 `control_time` 的配置信息：

- 字段 `velocity` 为必填项。
- 字段 `acceleration` 是可选项，但某些节点可能需要使用。
  - 如果使用此字段，则必须将 `is_defined_acceleration` 设置为 `true`。
- 字段 `jerk` 是可选项，但某些节点可能需要使用。
  - 如果使用此字段，则必须将 `is_defined_jerk` 设置为 `true`。

### Control.msg

定义了一个控制命令消息，将 `Lateral.msg` 和 `Longitudinal.msg` 合并在一起。

该消息传递了期望车辆的综合控制状态在指定时间点 `control_time` 的配置信息：

- 如果定义了 `control_time`，则 `lateral` 和 `longitudinal` 字段中的 `control_time` 字段将被忽略。

### ControlHorizon.msg

定义了一组为未来时间范围计算的控制命令数组。

- 控制消息按从近到远未来的顺序排列 `[0 到 N)`，时间间隔为 `time_step_ms`。
- 数组的第一个元素包含此消息 `control_time` 的控制信号。
- 控制数组中每个元素的 `control_time` 字段可以被忽略。
