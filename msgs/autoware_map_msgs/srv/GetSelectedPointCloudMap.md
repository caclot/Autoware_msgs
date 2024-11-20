# 地图加载的 ID 查询

**cell_ids**: 要加载的地图 ID 数组 (字符串数组类型)

---

# 标头和新加载的 PCD 地图

**header**: 消息头部，包含时间戳和坐标系信息 (std_msgs/Header 类型)

**new_pointcloud_with_ids**: 新加载的带有 ID 的 PCD 地图 (PointCloudMapCellWithID 数组类型)

```xml
string[] cell_ids
---
std_msgs/Header header
PointCloudMapCellWithID[] new_pointcloud_with_ids
