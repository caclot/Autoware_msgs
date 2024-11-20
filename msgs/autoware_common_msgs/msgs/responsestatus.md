# ResponseStatus

```xml
# 错误码定义
uint16 UNKNOWN = 50000          # 未知错误
uint16 SERVICE_UNREADY = 50001  # 服务未准备好
uint16 SERVICE_TIMEOUT = 50002  # 服务超时
uint16 TRANSFORM_ERROR = 50003  # 坐标转换错误
uint16 PARAMETER_ERROR = 50004  # 参数错误

# 警告码定义
uint16 DEPRECATED = 60000       # 功能已废弃
uint16 NO_EFFECT = 60001        # 操作无效

# 变量
bool   success                  # 操作是否成功的标志，true 表示成功，false 表示失败
uint16 code                     # 操作返回的状态码，对应上述定义的错误或警告码
string message                  # 附带的消息信息，可用于描述具体的错误或警告内容
```
