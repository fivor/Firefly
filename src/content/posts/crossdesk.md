---
title: CrossDesk——完全免费的远程控制软件
published: 2026-01-25
pinned: false
description: CrossDesk 是一个轻量级的跨平台远程桌面软件，还支持 Web 端控制远程设备。
tags: [远程控制, crossdesk]
category: 软件
auther: Fivor
draft: false
date: 2026-01-25
image: "https://im.fivor.cc/file/wx/1769343752922_33.webp"
---

## 简介
CrossDesk 是一个轻量级的跨平台远程桌面软件，还支持 Web 端控制远程设备。CrossDesk 是 MiniRTC 实时音视频传输库的实验性应用，而 MiniRTC 是一个轻量级的跨平台实时音视频传输库。它具有网络透传，视频软硬编解码，音频编解码，信令交互，网络拥塞控制，传输加密等基础能力。

![](http://img.fivor.cc/2026-01-25/270b089f-325c-4b8b-9dd5-09ccf8e00cb5.png)

## 多平台支持

| 平台 | 最低版本 |
|------------|-----------------------|
| **Windows** | Windows 10 及以上 (64 位) |
| **MacOS** | macOS Intel 15.0 及以上 <br> macOS Apple Silicon 14.0 及以上 |
| **Linux** | Ubuntu 22.04 及以上 |

![](http://img.fivor.cc/2026-01-25/131616d7-cd59-4af6-8d36-05518b1e5aaa.png)

## 使用方法

下载软件安装以后，在菜单栏的 “**对端ID**” 处输入远端桌面的ID（被控制的电脑），点击右边的 “→” 即可发起远程连接。

![](http://img.fivor.cc/2026-01-25/affbfe42-4e5d-4528-9682-535b7a019788.png)

如果远端桌面设置了连接密码，则本端需填正确的连接密码才能发起远程连接。

发起连接前，可在设置中自定义配置项，如语言、视频编码格式等。

![](http://img.fivor.cc/2026-01-25/23c8b690-a112-463a-925b-16e100150845.png)

## Web 客户端
另外不想安装完整的客户端的话，可以直接用电脑或者手机的浏览器访问 CrossDesk 的官网。点击“Web 客户端”，然后一样输入 **远程设备 ID** 与 **密码**，点击连接即可远程控制电脑。
![](http://img.fivor.cc/2026-01-25/1ea303dc-d52d-48e2-887d-9671f6186a5c.png)

>[!NOTE]
>运行时如果客户端状态栏显示 **未连接服务器**，请先在 CrossDesk 的官网下载安装客户端，以便在电脑上安装所需的证书文件。

## 自托管服务器
除了使用官方的连接服务器，还可以直接自己搭建服务器，推荐使用Docker部署CrossDesk Server。搭建好以后需要在客户端里面进行设置：

1. 点击软件右上角设置，进入设置页面。
2. 点击`自托管服务器配置`按钮。
3. 输入`服务器地址`(**EXTERNAL_IP**)、`信令服务端口`(**CROSSDESK_SERVER_PORT**)、`中继服务端口`(**COTURN_PORT**)。
4. 后续如果自托管服务器被重置，或因其他原因导致证书更换，可以点击`重置证书指纹`按钮重置客户端保存的证书指纹。

## 下载链接

官网下载：
[Crossdesk](https://www.crossdesk.cn)