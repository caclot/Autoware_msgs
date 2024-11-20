

Longitudinal control message

纵向控制消息

Values are in the base_link frame in X axis

值是在 base_link 坐标系下的 X 轴方向

Positive values represent forward motion (+X)

正值表示向前运动（+X）

Negative values represent backward motion (-X)

正值表示前进运动（+X）


```


# 消息创建时间
builtin_interfaces/Time stamp

# 预期达到该配置状态的时间（可选）
builtin_interfaces/Time control_time

# 期望的车辆速度，单位：米/秒
float32 velocity

# 期望的车辆加速度，单位：米/秒²
float32 acceleration

# 期望的车辆变加速度（jerk），单位：米/秒³
float32 jerk

# 控制器已填写加速度值
bool is_defined_acceleration

# 控制器已填写变加速度值
bool is_defined_jerk

```