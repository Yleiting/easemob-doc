# 字节跳动小程序集成介绍

<Toc />

### 注册环信账号

开发者需要在环信管理后台 [注册并创建应用](/document/v2/privatization/uc_configure.html#创建应用)，来获取唯一 appKey，SDK 初始化时需要配置 appKey。

### 搭建字节跳动小程序开发环境

首先需要下载并安装 [开发者工具](https://microapp.bytedance.com/docs/zh-CN/mini-app/develop/developer-instrument/developer-instrument-update-and-download/)，然后按照字节跳动小程序的 [接入流程](https://microapp.bytedance.com/docs/zh-CN/mini-app/develop/guide/start/kick-off) 一步步创建一个小程序

### 配置服务器域名

小程序在发布前，需要配置合法域名。

登录字节跳动小程序 [开发者平台](https://microapp.bytedance.com/)，选择当前小程序（如果没有需要创建一个小程序），进入 “开发管理>开发设置” 页面按私有部署文档中的 **2.2开通防火墙白名单** 配置各服务“地址:端口”。
<!--
:::tip
request 合法域名：

1. https://a1.easemob.com
2. https://a2.easemob.com
3. https://a3.easemob.com
4. https://a4.easemob.com
5. https://a5.easemob.com
6. https://a1-chatfile.easemob.com
   :::

:::tip
socket 合法域名：

1. wss://im-api.easemob.com（2.0 IM SDK)
2. wss://im-api-wechat.easemob.com（3.0 IM SDK）
   :::

:::notice
为满足不同客户的业务需求，环信在多地部署了数据中心。不同数据中心的 REST API 请求域名、WebSocket 访问域名不同。请根据您所在数据中心进行配置。
:::

环信不同数据中心的 REST API 请求域名、WebSocket 访问域名：

| 数据中心    | REST API 请求地址 | WebSocket 访问域名           |
| ----------- | ----------------- | ---------------------------- |
| 国内 1 区   | a1.easemob.com    | im-api-wechat.easemob.com    |
| 国内 2 区   | a31.easemob.com   | im-api-wechat-31.easemob.com |
| 国内 VIP 区 | 请咨询商务经理    | 请咨询商务经理               |
| 客服专用    | 请咨询商务经理    | 请咨询商务经理               |

应用所在数据中心可以在环信用户管理后台>应用信息中查看：

![img](@static/images/applet/console.jpeg)
-->
### 集成 SDK

#### 下载 SDK

可以通过以下两种方式获取 SDK：

<!--- 通过官网 [下载 SDK](https://www.easemob.com/download/im)-->
- 从环信的 [github 仓库](https://github.com/easemob/webim-weixin-xcx) 中获取 SDK 中的文件

#### 引入 SDK

- 开始一个全新的项目
  1. 将下载的 SDK（src/sdk/）导入到自己的项目中。
  2. 引入 SDK：`import IMSDK from "../sdk/Easemob-chat-miniProgram";`
- 基于 Demo 二次开发

将下载的代码导入开发者工具即可运行起来。

#### 调用示例

```javascript
//使用示例
import SDK from "../sdk/connection"; // 2.0 SDK
import SDK from "../sdk/Easemob-chat-miniProgram"; // 3.0 SDK
```

#### 实例调用方式

实例化 SDK，并挂载在全局对象下

```javascript
//实例化 SDK 对象
const WebIM = (wx.WebIM = SDK);
WebIM.conn = new WebIM.connection({
  appKey: "your appKey",
  https: true, //是否使用 HTTPS
  url: "wss://im-api-wechat.easemob.com/websocket", // socket server (3.0 SDK)
  apiUrl: "https://a1.easemob.com", // rest server
  heartBeatWait: 30000, //心跳间隔
  autoReconnectNumMax: 5, //自动重连次数
  useOwnUploadFun: false, // 是否使用自己的上传方式（如将图片文件等上传到自己的服务器，构建消息时只传 URL）
});
```

IM 基本功能和 Web 端一致，请参考 Web 端文档。