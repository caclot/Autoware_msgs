# 地图加载的区域查询

**area**: 区域信息，查询将加载与该区域重叠的点云数据 (AreaInfo 类型)

**cached_ids**: 节点当前已经拥有的 PCD 地图的 ID 数组 (string[] 类型)

---

# 标头和点云数据

**header**: 消息头部，包含时间戳和坐标系信息 (std_msgs/Header 类型)

**new_pointcloud_with_ids**: 新加载的带有 ID 的点云数据数组 (PointCloudMapCellWithID[] 类型)

**ids_to_remove**: 客户端需要移除的地图 ID 数组 (string[] 类型)

```xml
AreaInfo area
string[] cached_ids
---
std_msgs/Header header
PointCloudMapCellWithID[] new_pointcloud_with_ids
string[] ids_to_remove
```
