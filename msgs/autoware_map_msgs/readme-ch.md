# autoware_map_msgs

该消息包包含与地图数据相关的消息类型和服务接口，主要用于地图加载、区域查询和点云数据的传输。

## AreaInfo.msg

该消息表示一个区域信息。它用于查询部分或差异地图的加载（参考 `GetPartialPointCloudMap.srv` 和 `GetDifferentialPointCloudMap.srv` 服务接口部分）。

## PointCloudMapCellWithID.msg

该消息包含带有 ID 的点云数据。

## PointCloudMapCellMetaDataWithID.msg

该消息包含带有 ID 的点云元数据。这些 ID 用于查询特定的 PCD 地图（参考 `GetSelectedPointCloudMap.srv` 服务接口部分）。

## GetPartialPointCloudMap.srv

给定一个区域查询（`AreaInfo`），响应应包含与查询区域重叠的 PCD 地图（每个地图附带唯一 ID）。

## GetDifferentialPointCloudMap.srv

给定一个区域查询和客户端节点已经拥有的 ID，响应应包含与查询区域重叠并且客户端节点尚未拥有的 PCD 地图（每个地图附带唯一 ID）。

设 $X_0$ 为客户端节点已经拥有的 PCD 地图 ID 集，$X_1$ 为与查询区域重叠的 PCD 地图 ID 集，${\rm pcd}(id)$ 为返回与 ID `id` 对应的 PCD 数据的函数。在这种情况下，响应将是：

- `loaded_pcds`: $\lbrace [id,{\rm pcd}(id)]~|~id \in X_1 \backslash X_0 \rbrace$
- `ids_to_remove`: $\lbrace id~|~id \in X_0 \backslash X_1 \rbrace$

($x \in A \backslash B \iff x \in A \wedge x \notin B$)

## GetSelectedPointCloudMap.srv

给定一组 ID 查询，响应应包含查询指定的 PCD 地图（每个地图附带唯一 ID）。在使用此接口之前，客户端节点需要接收 `PointCloudMapCellMetaDataWithID.msg` 元数据，以便根据 ID 查询相关信息。