# Learning OpenTelemetry Setting Up and Operating a Modern Observability System pp. 111-126

## Transforming, Scrubbing, and Versioning

修改属性或遥测信号

最常见的转换之一是修改发出的遥测数据中的属性值。移除或模糊处理敏感信息，组合现有的属性值创建新的合成属性，或者使用模式转换来确保 OpenTelemetry SDK 不同版本之间的语义约定属性的一致性。

信号转换也是成本控制策略的一个非常有效的部分

将追踪转换为指标，可以以保存原始追踪数据的一小部分成本存储这些指标多年

将日志转换为指标是一种使资源日志变得可操作的有效方式

## Transforming Telemetry with OTTL

...

如何通过有效分层去重遥测信号?

如果从直方图指标中获取准确的速率、错误、持续时间和吞吐量计数，那么通过优先只收集“慢”追踪，可以节省收集和存储“快”追踪的成本。

对于日志，与其摄取数百万条单独的日志行，不如在收集点去重并将它们转换为一个指标或一个更大的结构化日志。

如果使用的是基于列的数据存储来存储遥测数据, 与其将瞬时指标作为单个事件发送到数据存储，不如在记录跨度时读取这些指标的值，并将它们作为属性添加到跨度中。