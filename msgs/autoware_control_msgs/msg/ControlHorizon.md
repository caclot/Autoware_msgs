


## 控制消息的计算方式：

消息包含一个控制命令数组，这些控制命令表示未来一段时间内的控制动作。数组的第一个元素代表当前时刻的控制信号，其后的元素则代表未来时刻的控制信号。

## 时间步长 (time_step_ms)：

每个控制命令之间的时间差，以毫秒为单位。通过该字段，系统可以知道控制命令之间的时间间隔。这个时间间隔是固定的。

## 控制命令数组 (controls)：

数组中的每个元素都代表车辆在未来某个时刻需要达到的控制状态。第一个元素代表当前时刻的控制状态，后续元素则依次代表未来时刻的状态。

## 消息结构：

时间戳 (stamp) 和控制时间 (control_time)：
stamp 表示消息的生成时间，control_time 则表示第一个控制命令 (controls[0]) 应该在什么时间点达到预期的状态。control_time 提供了一个全局的时间框架，而数组中的每个控制命令则根据 time_step_ms 推算出它们的实际时刻。



```xml


# Time this message was created
builtin_interfaces/Time stamp

# Time when controls[0] configuration state is expected to be achieved in
builtin_interfaces/Time control_time

# Time difference between consecutive elements of the controls array in milliseconds
float32 time_step_ms

Control[] controls
```

Control messages calculated for a future horizon

为未来时间范围计算的控制消息

Control messages are ordered from near to far future [0 to N) with time_step_ms increments.

控制消息按时间步长 `time_step_ms` 从最近的未来到最远的未来依次排列，范围是 [0 到 N)。

First element of the array contains the control signals at the control_time of this message.

数组中的第一个元素包含在当前消息的 `control_time` 时刻的控制信号。

The control_time field in each element of the controls array can be ignored.

每个控制命令数组中元素的 `control_time` 字段可以忽略。
