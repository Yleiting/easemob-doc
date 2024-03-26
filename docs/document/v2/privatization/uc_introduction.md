# 产品概述

<Toc />

环信即时通讯私有化服务是基于 IM 核心技术实现的可私有化部署解决方案。本方案可适配内网物理服务器集群、公有云以及私有云等任意部署环境，提供功能完备、安全可靠、易于扩展的即时通讯平台。整体通讯平台架构主要由三部分组成，分别为客户端、服务端、Web 控制台。

- **客户端**：采用 SDK 形式，对核心通信模块进行封装，提供场景功能接口，覆盖多种平台（包括：Android、iOS、Web、小程序、 Windows/Mac OS、Linux），支持快速集成终端用户应用。
- **服务端**：采用 Java 和 Erlang 语言编写，可支持用户高并发连接和系统动态调配，高效处理用户长连接相关的服务和用户管理、推送等无状态服务。同时提供服务端 REST API 和 Java Server SDK 接口，便于完成即时通讯软件中服务的控制、数据的转发存储工作。
- **Web 控制台**：是基于 B/S 模式的可视化操作平台，可支持开通与配置应用功能，查询各类 IM 服务情况，管理与维护用户体系（增、删、改、查），满足系统管理员、开发者等多种业务角色使用需求，提升业务集成与运营管理效率。


## 平台架构

![环信 IM 后台](@static/images/privitization/framework.jpg?w=50)


## 集成概述

当私有化服务部署后，开发者主要需要了解服务器端集成和客户端集成内容。

![img](@static/images/product/integration-overview.png)

服务端集成请看：[环信即时通讯 REST API 概览](/document/v2/server-side/overview.html)。

客户端 Demo 体验请查看：

[Android Demo（EaseIM App）体验](/document/v2/android/demo.html)

[iOS Demo（EaseIM App）体验](/document/v2/ios/demo.html)

客户端集成请查看相应的环信 SDK 开发文档：

[环信即时通讯 IM Android 快速开始](/document/v2/android/quickstart.html)；

[环信即时通讯 IM iOS 快速开始](/document/v2/ios/quickstart.html)；

[环信即时通讯 IM Web 快速开始](/document/v2/web/quickstart.html)。

## 功能概述

用环信即时通讯能实现以下功能：

### 单聊

环信单聊，支持丰富的消息类型，以及离线消息、漫游消息等功能。

### 群聊

环信群聊，支持丰富的消息类型，支持完整的群组管理能力，包含发布群公告、设置群角色等。

### 用户管理

提供用户体系管理能力，如：好友管理、黑名单管理等。支持用户资料存储，包括：头像、昵称、自定义用户信息等。

### 丰富的消息类型

支持单聊/群聊中，发送文本、表情、图片、语音、视频、地理位置、文件，以及红包和礼物等的自定义消息。

### 第三方消息推送

消息推送指当应用在后台运行，或进程被杀时，用户处于离线状态，新消息在发送至环信服务器后，会被转发至第三方推送服务器进行推送，以确保该消息依然可以送达客户端。推送消息在安卓端是使用 Firebase Cloud Message(FCM) 实现，在 iOS 端使用 Apple Push Notification service(APNs) 实现。

### 多端消息同步

环信支持一个账号同时登录多台设备，可实现终端用户的消息通过服务器保存和同步，保证各端均能收发消息同步。

### 消息撤回

消息发出后可以进行消息撤回，提供 SDK 和 REST API 端两种撤回方式。

## 适用场景

环信适用于端到端实时消息沟通的场景：

- 应用内聊天（如：陌生人社交、相亲等）
  - 支持丰富的消息类型、好友关系管理
  - 支持群管理能力、群公告设置、群角色设置等
- 应用内通知
  - 支持广播消息、自定义通知消息等
  - 支持用户管理，包括储存用户信息、用户封禁等
- 视频/语音直播
  - 支持聊天室管理能力
  - 支持丰富类型的聊天室消息，包括弹幕、红包、礼物等
- 企业协作
  - 支持用户管理，设置企业组织架构、好友关系管理
  - 支持群管理能力、群公告设置、群附件发送、群角色设置等
- 买家卖家沟通
  - 支持订单通知、问候语设置、自定义消息发送
  - 支持卖家内部管理、公告设置、成员管理等
- 线上问诊
  - 支持丰富的消息类型，图文病情描述、语音消息等
  - 支持用户信息存储、用户身份管理等

## 产品优势

环信主要有以下优势：

### 部署多样化

环信即时通讯系统支持 Linux 裸系统、容器化等多种部署方式。不仅可以提供更灵活、更便捷、更稳定的平台性能，同时容器化部署可实现自动部署，具备服务自动发现、服务自动负载均衡等特点。

### 高可用

环信即时通讯系统具备高可用特性，当系统内某一个节点或主机出现宕机后，该故障节点上的所有服务会自动转移到其他节点上而不会引发服务中断，保障系统可用性。

### 易扩展

环信即时通讯系统服务架构支持弹性扩展，系统内所有资源可在各节点之间实现灵活调度，当 CPU、内存等计算资源利用率较高时，可通过横向添加 node 实现平滑扩容。

### 安全性

环信即时通讯系统实现通讯全流程安全加密，支持客户端敏感信息加密存储、服务器密钥权限管理、消息传输过程私有协议加密以及用户信息隐私保护等措施。

### 国产化

环信即时通讯系统严格遵循国家法律法规和技术标准规范，积极响应国内自主可控、安全可控要求，从 IT 基础设置、操作系统、数据库等方面进行国产化升级，满足信创环境部署要求。

### 多平台

环信即时通讯 IM 支持 Android、iOS、Web 等平台，而且各平台之间可互通。下表为即时通讯支持的各平台版本：

| 平台     | 支持的版本                                   |
| ------------ | ------------------------------------------------------------ |
| Android      | Android 5.0 或以上版本（API 级别 21 或以上）   |
| iOS          | iOS 10.0 或以上版本                                            |
| Web          | <br/> - Internet Explorer 9 或以上 <br/> - FireFox 10 或以上 <br/> - Chrome 54 或以上 Safari 6 或以上<br/> - Edge 12 或以上 <br/> - Opera 58 或以上<br/> - iOS Safari 7 或以上<br/> - Android Browser 4.4 (KitKat) 或以上 |
| Unity        | Unity 2017 或以上版本                                         |
| Windows      | Windows 10 或以上版本                                       |
| React Native | React Native 0.63.4 或以上版本                              |
| Flutter      | Flutter 2.10                                                 |