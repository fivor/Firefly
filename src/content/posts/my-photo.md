---
title: TRAE零基础AI编程做一个在线相册网站
published: 2026-02-01
pinned: false
description: 一个基于 Cloudflare R2 + Workers + React 构建的现代化、高性能、Serverless 个人相册系统。
tags: [TRAE, AI, Github]
category: 文章
auther: Fivor
draft: false
date: 2026-02-01
image: "https://img.fivor.cc/2026-02-01/95260f33-0fee-433b-92c7-ef43f16e25e2.png"
---

## 背景
前不久看到一个活动，为庆祝上线一周年，TRAE国际版全部用户限免一个月！即从2026年1月14日 10:00 起，TRAE国际版全部用户赠送权益（不少于1个月Pro会员的用量）！TRAE 是字节跳动官方推出的AI原生IDE，深度融合AI能力，内置SOLO模式，就是Coding Agent，可以直接让AI写代码搭建项目。还有半个月时间，感兴趣的小伙伴可以去体验～

- **Free 用户：** 账号增加600次Fast Request，有效期至北京时间2月14日 10:00
- **Pro 用户：** 账号增加800次Fast Request，有效期至北京时间3月14日 10:00

## AI编程

### 准备工作

首先去官网 https://www.trae.ai 下载TRAE国际版（不是国内版），然后在官网登陆自己的账号，点击右上角“Claim Anniversary Gift”，然后拉到最下点击“claim”就可以了。

![](http://img.fivor.cc/2026-02-01/932156fc-9506-4aa0-8c59-ed7884eb95a4.png)

接着就是正常安装TRAE，安装好以后登陆账号，进入主界面，可以选择打开现有的文件夹，或者克隆Git仓库。之前一直都是Fork别人的项目，这次想自己搭建一个项目，也算是从0到1的突破。于是在电脑上新建一个文件夹Photo，在TRAE里选择打开这个文件夹。

电脑默认是进入IDE界面，点击左上角切换到SOLO模式。SOLO里有两个智能体，作为新手的我，直接就选择SOLO Builder。如果想换智能体，左下角可以随时切换。

- **SOLO Coder：** 面向复杂项目开发的智能体。SOLO Coder 能够助力你高效完成从需求迭代到架构重构的全流程开发工作。
- **SOLO Builder：** 快速构建专业且功能完善的 Web 应用。你只需用自然语言描述需求，SOLO Builder 便会自动根据任务选择最合适的 AI 模型、分析需求、生成 PRD、编写代码，并产出可预览成果。

### 开始编程
进入SOLO模式后，左侧就是和AI智能体对话的界面，直接告诉AI你想要实现什么功能，或者直接问他问题也行。中间就是编辑器和终端，主要写代码的地方。比如这里我就是直接让AI写了个README文档，然后我看这个文档，才知道项目里具体是咋回事。是的，我自己的项目，我还要看说明文档。在绑定Github账号后，可以让AI把改好的代码自动提交。

![](http://img.fivor.cc/2026-02-01/c82092cf-00c8-49b9-bb46-070bdb52d161.png)

接下来就是看你具体想要实现什么功能，我这次是想做一个在线相册的网站，可以在浏览器里上传和查看照片，有点像古早的QQ空间。于是直接告诉AI，我想要做一个在线相册网站，需要有哪些功能，可以加一些限制条件，比如网站的功能尽量前端完成，不要服务器，0成本搭建。如果觉得自己写的不够详细，可以点击右下角的“优化输入内容”，让AI把你的想法补充完整，也可以选择不同的AI模型，修改好以后发给AI。我也不知道具体有什么差异，就直接选默认的推荐模型。

![](http://img.fivor.cc/2026-02-01/66df529b-ad9a-4b91-9b57-0d018c22f1fb.png)

接下来AI就开始大展身手，他会根据需求，创建文件，开始写代码。全部完成后，AI会再整理一个概要，他做了哪些事情，实现了哪些，还需要做哪些。关键他写代码时间很快，每次最多几分钟，包括问他很复杂的问题，也基本能秒回，效率高。这种能给予即时反馈的感觉真的很上头，就像在玩游戏一样。自己可以先搭好项目的框架，再通过不断的对话，慢慢往里面补充功能，直接一步到位也不现实。

这个时候你就可以扮演一个非常刁钻的甲方，让AI不停的改代码，直到达到你的目标。或者有任何不明白的地方，直接对话框里问AI，他都会详细回答，而且还会根据项目的实际情况和上下文回答，回答的质量非常高。对于一些简单的项目，感觉AI完全可以取代程序员，除了不能帮我测试，其他的都可以完成。

### 调试和优化
这个项目前前后后花了好几天时间，大部分时间都是花在了改Bug和优化上。比如我电脑上有HEIC格式的图片，在上传/缩略图/完整大图三个界面，全都不能正常显示，于是就让AI反反复复改代码。最后刚把缩略图改好，可以正常显示，但是大图显示又不正常，改了几次，实在不行。就只能放弃支持HEIC格式的文件，直接不允许上传，从源头解决这个问题。

由于我这个方案的照片都是存储在Cloudflare R2上，前端网页是放在Github Pages，有时候上传的照片很大，国内直接访问速度很慢，于是就会看到一直显示加载中，很影响体验。后来改为部署在Vercel上，Cloudflare缓存策略也进行调整，太大的照片会压缩后再上传，一套组合拳下来，现在访问会快很多。不想备案，不想花钱，就只能多折腾了。

## 成果
这个就是目前的成果，网站功能很简单，主要就是上传/查看/下载照片。
![](http://img.fivor.cc/2026-02-01/6a66b1f7-325c-4115-a0eb-672054c77729.png)

## README
以下为Github上本项目README的部分内容，感兴趣的小伙伴可以去Github上查看完整内容。这个只是一个初版，我后续可能还会往网站里加功能。

### ✨ 核心特性

*   **Serverless 架构**：后端完全运行在 Cloudflare Workers 上，无需服务器维护，成本极低。
*   **全球加速**：利用 Cloudflare R2 存储照片，配合 CDN 全球边缘缓存，加载速度飞快。
*   **现代化 UI**：基于 React + Tailwind CSS 构建，支持深色/浅色模式，响应式设计适配移动端。
*   **多格式支持**：支持 JPG, PNG, WEBP, GIF, AVIF, TIFF, BMP 等多种图片格式上传与预览。
*   **智能压缩**：前端/后端双重压缩优化，自动生成 WebP 缩略图，节省流量并提升速度。
*   **相册管理**：支持创建多级相册、拖拽上传、批量管理（移动、删除、恢复）。
*   **访客系统**：支持生成专属访客账号，可精确控制每个访客能看到的特定相册。
*   **隐私保护**：所有 API 请求均经过 JWT 鉴权，支持回收站机制防止误删。

### 🛠️ 技术栈

**前端 (Frontend):**
*   **框架**: React 18 + TypeScript + Vite
*   **样式**: Tailwind CSS + Lucide React (图标)
*   **状态管理**: Zustand
*   **路由**: React Router v7
*   **组件库**: React Photo View (灯箱), React Dropzone (上传)
*   **部署**: Vercel (推荐) / GitHub Pages / Cloudflare Pages

**后端 (Backend):**
*   **运行时**: Cloudflare Workers
*   **存储**: Cloudflare R2 (对象存储)
*   **鉴权**: JWT (JSON Web Tokens)
*   **图像处理**: @jsquash (WebAssembly 图像压缩/解码)

### 🚀 快速开始

#### 1. 前置准备
*   一个 Cloudflare 账号。
*   一个域名（托管在 Cloudflare 上以获得最佳体验）。
*   Node.js 环境 (v18+)。

#### 2. 后端部署 (Cloudflare Workers)

1.  **安装 Wrangler CLI**:
    ```bash
    npm install -g wrangler
    ```

2.  **配置 R2 存储桶**:
    *   在 Cloudflare 后台创建一个 R2 Bucket，命名为 `photo-gallery`。
    *   在 Bucket 设置中绑定自定义域名（如 `im.example.com`），并开启 "Public Access"（或者配置 Access 策略）。
    *   **重要**: 在 Cloudflare 域名 DNS 设置中，为该图片域名配置 Page Rule: `Cache Level: Cache Everything`，以开启 CDN 缓存。

3.  **配置 Wrangler**:
    修改 `wrangler.toml`:
    ```toml
    name = "photo-gallery-worker"
    # 修改为你的图片域名
    [vars]
    R2_PUBLIC_DOMAIN = "https://im.example.com" 
    ```

4.  **设置密钥**:
    ```bash
    wrangler secret put ADMIN_PASSWORD  # 设置管理员密码
    wrangler secret put JWT_SECRET      # 设置 JWT 签名密钥（随机字符串）
    wrangler secret put VISITOR_PASSWORD # 设置全局访客密码（可选）
    ```

5.  **部署后端**:
    ```bash
    npm run deploy:worker
    ```
    记下部署后的 Worker URL（如 `https://photo-api.yourname.workers.dev`）。

#### 3. 前端部署 (Vercel)

1.  **Fork 本仓库**。
2.  **在 Vercel 中导入项目**。
3.  **配置环境变量**:
    *   `VITE_API_BASE`: 填入你的 Worker URL (例如 `https://photo-api.yourname.workers.dev/api`，注意带 `/api` 后缀)。
4.  **部署并绑定域名**:
    *   部署完成后，绑定你的前端域名（如 `a.example.com`）。
    *   由于 Vercel 自带全球 CDN，建议在 `vercel.json` 中保持默认缓存策略。

### ⚙️ 环境变量说明

| 变量名 | 类型 | 说明 |
| :--- | :--- | :--- |
| `VITE_API_BASE` | Frontend Env | 后端 API 地址，用于前端请求 |
| `R2_PUBLIC_DOMAIN` | Backend Var | R2 存储桶绑定的公开域名 |
| `ADMIN_PASSWORD` | Backend Secret | 管理员登录密码 |
| `JWT_SECRET` | Backend Secret | 用于生成 Token 的密钥 |

### 小结
我自己不是程序员，也不会写代码，但以前觉得有些网站或者软件看着功能都很简单，想着开发一个应该也不是很难。但直到真的开始编程，即使还只是让AI编程，我自己没有写一行代码，才发现编程是真的难，各种想都想不到的Bug。

不得不说，现在AI也真的是厉害。程序员写代码开发AI，然后现在AI也会写代码开发了，那以后能不能让AI自己优化自己，直接开始迭代进化，脱离人类的控制，科幻电影里的情景终将发生在现实。
