# MyCloud 个人云盘项目说明
## 项目概述
MyCloud 是一个个人云盘应用，旨在为用户提供高效、安全的文件存储、管理和分享功能。通过该应用，用户可以在云端存储文件，并随时随地进行访问和管理。该应用的前端使用 Flutter 开发，后端使用 SpringBoot 构建，文件存储与管理则通过 MinIO 实现。

## 技术栈
### 前端：

+ Flutter：用于构建跨平台的移动应用（iOS/Android）。
+ Dart：Flutter 的编程语言，用于实现应用的逻辑与界面。
### 后端：

+ SpringBoot：用于构建 RESTful API 服务，提供数据接口与业务逻辑处理。
+ MySQL：用于存储用户基本信息和操作记录。
### 文件存储：

MinIO：高性能的分布式对象存储服务，作为文件存储系统，提供文件上传、下载、删除、列举等功能。
功能
1. 用户管理
   用户可以通过注册、登录、登出管理自己的账户。
   支持查看和修改用户个人信息。
2. 文件管理
   用户可以上传文件至云端。
   用户可以下载、删除云端文件。
   支持文件夹管理，允许用户在云端创建文件夹并进行文件分类。
   文件可以通过 URL 分享给其他用户。
3. 个人空间
   每个用户拥有独立的个人空间，可以存储自己的文件。
   用户可以查看文件的详细信息，包括文件名、上传时间、大小等。
4. 文件搜索与过滤
   用户可以通过关键词搜索自己的文件。
   支持按文件类型、日期等过滤文件。 
## 系统架构
1. 前端架构
   前端使用 Flutter 构建，分为以下模块：

登录模块： 用户登录和注册功能。
文件模块： 展示文件列表、上传文件、下载文件、删除文件等功能。
设置模块： 允许用户管理个人资料和账号设置。
2. 后端架构
   后端采用 SpringBoot 构建，提供以下服务：

用户管理服务： 提供用户注册、登录、信息更新等接口。
文件管理服务： 提供文件上传、下载、删除、列出等接口。
安全服务： 负责用户认证和授权，确保数据的安全性。
3. 文件存储架构
   MinIO 提供高可用的对象存储，支持多种存储策略，文件以对象的形式存储在 MinIO 中。每个文件会有一个唯一的存储路径，用户上传的文件通过 MinIO 存储，文件元数据存储在 MySQL 中。

## 项目部署
1. 前端部署
   使用 Flutter 构建 Web 或移动应用。
   编译后，应用可以直接部署到服务器，或发布到各大应用商店（如 Google Play 或 Apple App Store）。
2. 后端部署
   使用 SpringBoot 构建后端服务，部署时需要配置数据库连接和 MinIO 服务。
   可以使用 Docker 容器化部署，或直接将服务部署到云服务器中。
3. 文件存储部署
   安装并配置 MinIO 服务，确保文件存储路径、权限等设置正确。
   配置 MinIO 的访问密钥和端点，后端服务通过 API 访问 MinIO 进行文件操作。
## 环境要求
   开发环境：

+ JDK 17+（用于构建和运行 SpringBoot 后端）
+ Node.js & Flutter SDK（用于构建前端应用）
+ MySQL 5.7+（用于存储用户数据）
+ MinIO（用于文件存储）
## 生产环境：
+ 云服务器（如 AWS、阿里云等）
+ Docker（可选，适用于容器化部署）