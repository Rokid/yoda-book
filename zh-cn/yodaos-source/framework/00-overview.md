在 [YodaOS][] 系统中，分为不同的模块框架，它们总是互相协作以完成不同场景下的任务，在本章节中将对其一一介绍。

#### [应用框架](./01-application.md)

应用框架定义了 [YodaOS Application][] 协议与基础应用层接口，并且实现了应用与系统组件的管理。

#### [多媒体（音频）](./02-multimedia.md)

多媒体框架赋予了系统播放多媒体（音频）文件的能力，支持了包括语音合成（TTS）播放、歌曲播放、音效播放等多项任务。

#### [按键](./03-input-event.md)

按键框架提供了从应用层到框架层监听设备按键的能力，开发者可以通过该框架提供的 基于 JSON 的 DSL 来定制自己的产品按键。

#### [网络](./04-networking.md)

网络框架定义了智能设备与网络相关的行为，并且提供了多种配网协议（Wi-Fi 热点和 BLE），以及对于多种网络制式状态的控制
与选择，同时负责将当前网络状态进行广播。

#### [蓝牙](./05-bluetooth.md)

蓝牙框架为网络框架的配网模块提供 BLE 支持，并且与多媒体框架与应用框架一起提供了蓝牙音乐播放功能。

#### [语音交互接口](./06-voice-interface.md)

[YodaOS][] 抽象了不同的语音交互服务，如 Alexa、Google Assistant，每个 [Voice Interface Driver][] 就是按照
语音交互接口实现的“驱动”模块。

#### [硬件抽象接口](./07-hal.md)

[YodaOS][] 沿用了 Android Hardware Framework，这对于熟悉 Android 的开发者来说，可以更加轻松地切入到 [YodaOS][]
的移植中来。

[YodaOS]: https://github.com/yodaos-project
[YodaOS Application]: /yodaos-source/02-glossary.md#yodaos-application
[Voice Interface Driver]: /yodaos-source/02-glossary.md#voice-interface-driver
