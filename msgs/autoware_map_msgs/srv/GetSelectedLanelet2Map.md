# 选择加载的 OSM 文件 ID

**cell_ids**: 选定加载的 OSM 文件 ID 数组 (字符串数组类型)

---

# 标头和新加载的 Lanelet 地图

**header**: 消息头部，包含时间戳和坐标系信息 (std_msgs/Header 类型)

**lanelet2_cells**: 新加载的 Lanelet 地图数据 (autoware_map_msgs/LaneletMapBin 类型)

```xml
string[] cell_ids
---
std_msgs/Header header
autoware_map_msgs/LaneletMapBin lanelet2_cells
