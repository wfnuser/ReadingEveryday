# Learning OpenTelemetry Setting Up and Operating a Modern Observability System pp. 0-10

微服务架构虽然提供了灵活性和可扩展性，但也引入了新的复杂性。传统的监控工具设计用于单体应用程序，往往难以捕捉服务之间复杂的交互和依赖关系。这种缺乏一致性可见性的情况导致了可见性差距，使得难以定位性能瓶颈、诊断问题并确保应用程序的健康状况。

有效的可观测性的关键在于高质量的遥测数据。

## ch1.The State of Modern Observability

将单独的日志、指标和跟踪转化为一致、统一的信息图。

在最高层面上，分布式系统由资源和事务组成：

- 资源
  - 这些是构成系统的所有物理和逻辑组件。物理组件如服务器、容器、进程、内存、CPU 和网卡，都是资源。逻辑组件如客户端、应用程序、API 端点、数据库和负载均衡器，也都是资源。简而言之，资源是系统实际构建的所有内容
- 事务
  - 这些是协调和利用系统资源为用户工作而发出的请求。通常，事务由一个真实的人启动，他们在等待任务完成。预订航班、叫车和加载网页都是事务的例子

如何观察这些分布式系统？除非它们发出遥测数据，否则无法观察它们。遥测数据是描述系统正在做什么的数据。

区分用户遥测和性能遥测：

- 用户遥测User telemetry
  - 有关用户通过客户端与系统交互的数据：按钮点击、会话持续时间、客户端主机机器的信息等等。你可以使用这些数据来了解用户如何与电子商务网站交互，或者访问基于网络的应用程序的浏览器版本分布情况
  - 如，有人将鼠标光标悬停在结账按钮上多长时间
- 性能遥测Performance telemetry
  - 主要不是用于分析用户行为，而是为操作人员提供有关系统组件行为和性能的统计信息。性能数据可以来自分布式系统中的不同来源，为开发人员提供一条“面包屑轨迹”，将原因与结果连接起来
  - 如，加载结账按钮本身花了多长时间，以及系统在此过程中使用了哪些程序和资源

用户遥测和性能遥测都有不同类型的信号。信号是一种特定形式的遥测数据。包括事件日志，系统指标，持续分析。

每种信号由两个部分组成：

- 程序内部发出遥测数据的检测代码
- 用于通过网络将数据发送到分析工具的传输系统，实际的观察发生在分析工具中

发出数据的系统和分析数据的系统是相互独立的。遥测是数据本身，而分析是对数据所做的处理。

遥测加上分析等于可观测性。