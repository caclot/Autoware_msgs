# 带有 ID 的点云数据

- **cell_id**: 点云单元格的唯一标识符 (字符串类型)
- **pointcloud**: 点云数据 (sensor_msgs/PointCloud2 类型)
- **metadata**: 点云地图单元格的元数据 (PointCloudMapCellMetaData 类型)

```xml
string cell_id
sensor_msgs/PointCloud2 pointcloud
PointCloudMapCellMetaData metadata
