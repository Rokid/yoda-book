术语表（Glossary）
===============

#### AFS

AFS 是 Application Framework Service 的缩写，表示应用框架服务，它面向开发者提供了：应用管理，核心开发接口，以及组件化接口等功能。

#### flora

YodaOS 使用 [yodaos-project/flora](http://github.com/yodaos-project/flora) 作为系统 IPC 库，详情请见链接。

#### openwrt

[openwrt][] 是一款针对嵌入式设备的 Linux 发行版，YodaOS 构建于 [openwrt][] 之上，所以关于
编译框架相关的都继承自 [openwrt][]。

#### Protocol Fauna

YodaOS 运行时协议，提供了应用注册（初始化）、运行时调用和事件订阅的功能，具体文档可以查看 [docs/protocol-fauna.md](https://github.com/yodaos-project/yodart/blob/master/docs/protocol-fauna.md)。

#### Voice Interface Driver

语音交互（Voice Interface）依赖不同的云端提供服务，与之对应的接口不同，因此在 YodaOS 中，我们需要一个称作
Voice Interface Driver 的模块来适配不同的语音交互层协议，其主要工作就是将云端的基础指令如 TTS、ASR 或控制
类指令转译为本地的 [YodaOS Message](#yodaos-message)，从而完成一次完整的交互。

#### YodaOS Application

每个应用通过 [YodaOS Message](#yodaos-message) 的方式监听消息，来完成自己的业务逻辑，内置的应用
包括：cloud-player、system、volume、launcher 等。

#### YodaOS Component

用于连接系统框架层与应用框架层的组件，目前的组件列表包括 [runtime/component](https://github.com/yodaos-project/yodart/tree/master/runtime/component)，提供了包括：应用加载、语音焦点、广播、计时器、内存管理等核心功能。

#### YodaOS Message

在 YodaOS 中的通讯（IPC）方式，分别分为：

- YodaOS URL，如 `yoda-app://cloud-player/play-tts-stream`，单向调用的方式，一般用于语音或硬件指令下发；
- YodaOS Event，单向的方式，与 URL 不同的是 Event 使用订阅的方式，支持一对多；
- YodaOS Function，双向调用，类似于请求/响应模型，被调用者需要在一定时间内写入返回值；

以上的三种方式，都使用了同一种 IPC 技术：[flora](#flora)。

#### YodaOS Package

YodaOS Package 是系统中一种软件单元，包含 JavaScript 文件、[N-API][] 桥接模块和 package.json。

[openwrt]: https://openwrt.org/
[N-API]: https://nodejs.org/dist/latest/docs/api/n-api.html
