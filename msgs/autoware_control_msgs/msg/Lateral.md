


Lateral control message for Ackermann-style platforms

- Ackermann 风格平台的横向控制消息

Note regarding tires: If the platform has multiple steering tires, the commands

given here are for a virtual tire at the average lateral position of the steering tires.

- 关于轮胎的说明：如果平台有多个转向轮，这里给出的命令适用于一个虚拟轮胎，该轮胎位于所有转向轮的平均横向位置。

Look up Ackermann Bicycle Model for more details

- 更多细节请查阅 Ackermann Bicycle模型


Positive values represents left inclination (if forward)

- 正值表示向左倾斜（如果车辆向前行驶）

Negative values represents right inclination (if forward)

- 负值表示向右倾斜（如果车辆向前行驶）



```xml

# 消息创建的时间
builtin_interfaces/Time stamp

# 期望在该时间点达到此配置状态的时间（可选）
builtin_interfaces/Time control_time

# 期望的横向加速度
float32 steering_tire_angle

# 转向轮的期望角度，单位为弧度（rad）
float32 steering_tire_rotation_rate

# 控制器是否已填写转向轮角度变化率的值
bool is_defined_steering_tire_rotation_rate

```