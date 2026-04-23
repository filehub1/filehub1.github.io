# FileHub Docker — 您的私有云文件搜索服务器

**一行命令，在 NAS、树莓派或任何服务器上搭建私有文件搜索引擎**

![FileHub Docker](https://img.shields.io/docker/v/exiahuang/filehub-server?label=FileHub&style=flat-square)
![Docker Pulls](https://img.shields.io/docker/pulls/exiahuang/filehub-server?style=flat-square)
![MIT License](https://img.shields.io/badge/license-MIT-green?style=flat-square)

## 为什么要用 Docker 部署 FileHub？

| 传统方式 | FileHub Docker |
|---------|----------------|
| 需要在每台设备安装客户端 | 一次部署，多设备访问 |
| 文件分散在不同硬盘/设备 | 集中索引，统一搜索 |
| 网盘搜索慢、上传麻烦 | 本地速度，即搜即得 |
| 文件存储在第三方云端 | 数据完全私有，不上传云 |

## 快速开始

```bash
# 一行命令启动
docker run -d -p 6543:6543 -v /your/data:/data exiahuang/filehub-server:latest
```

然后浏览器打开 `http://localhost:6543`

**就这么简单！** 无需配置，无需安装依赖，开箱即用。

## 支持的场景

### 🏠 家庭媒体中心
- 索引 NAS 上的所有电影、照片、音乐
- 用手机搜索 "去年暑假照片" → 直接找到
- 局域网内任意设备访问

### 🖥️ 办公室文档库
- 索引共享盘的所有工作文档
- 支持 PDF、Word、Excel 全文预览
- 模糊搜索，文件名记不全也能找到

### 🖧 服务器/开发环境
- 索引服务器日志、配置文件
- 代码搜索，支持语法高亮预览
- API 开放，可集成到其他系统

## 支持的文件预览

- 📄 **文档**: PDF, Word (.doc/.docx), Excel (.xlsx), PowerPoint (.pptx)
- 🖼️ **图片**: PNG, JPG, GIF, WebP, SVG
- 🎬 **视频**: MP4, AVI, MKV (浏览器直接播放)
- 🎵 **音频**: MP3, WAV, FLAC (背景播放)
- 📝 **代码**: 支持 100+ 种语言的语法高亮
- 📋 **文本**: Markdown, JSON, XML, CSV, TXT

## 配置选项

### 基本用法（推荐）

```bash
docker run -d \
  -p 6543:6543 \
  -v /your/data:/data \
  exiahuang/filehub-server:latest
```

### 自定义端口和数据目录

```bash
docker run -d \
  -p 8080:6543 \
  -v /mnt/media:/data \
  exiahuang/filehub-server:latest
```

### 启用管理员模式（Windows MFT 加速）

```bash
docker run -d \
  -p 6543:6543 \
  -v /your/data:/data \
  exiahuang/filehub-server:latest \
  --use-admin-mode
```

### 使用 Docker Compose

创建 `docker-compose.yml`:

```yaml
version: '3'
services:
  filehub:
    image: exiahuang/filehub-server:latest
    container_name: filehub
    restart: unless-stopped
    ports:
      - "6543:6543"
    volumes:
      - /path/to/your/data:/data
    environment:
      - TZ=Asia/Shanghai
```

启动：
```bash
docker-compose up -d
```

## 数据持久化

FileHub 的配置文件存储在容器内的 `~/.filehub`。如需持久化配置：

```bash
# 挂载配置目录
docker run -d -p 6543:6543 \
  -v /your/data:/data \
  -v /your/config:/root/.filehub \
  exiahuang/filehub-server:latest
```

## 局域网访问

部署后，同一 Wi-Fi 下的所有设备都可以访问：

1. 在 FileHub 界面底部查看局域网地址
2. 或扫描界面显示的二维码
3. 手机/平板直接浏览器打开，扫码即用

**可选：启用 Basic 认证保护**
```yaml
# 配置文件 ~/.filehub
lanUsername: your-username
lanPassword: your-password
```

## 性能对比

| 场景 | Windows 搜索 | FileHub Docker |
|------|-------------|----------------|
| 首次索引 100 万文件 | 5-10 分钟 | 1-3 分钟 |
| 搜索响应时间 | 100-500ms | <10ms |
| 内存占用 | 200MB+ | <150MB |
| 支持平台 | 仅 Windows | 任意平台 |

## 技术规格

- **镜像大小**: ~80MB
- **内存要求**: 最低 256MB，推荐 512MB+
- **CPU**: 任意 x86/arm64 架构
- **网络**: 需要局域网连接
- **存储**: 根据索引文件数量，约 1MB/万文件

## 常见问题

### Q: 如何查看日志？
```bash
docker logs filehub
```

### Q: 如何更新到最新版本？
```bash
docker pull exiahuang/filehub-server:latest
docker-compose up -d
```

### Q: 支持 ARM 架构吗？
**是的！** 镜像同时支持 x86_64 和 arm64，包括树莓派。

### Q: 数据安全吗？
- 所有数据存储在本地，不上传任何云服务
- 可选 Basic 认证保护局域网访问
- HTTPS 支持（需配合反向代理）

## 获取帮助

- 📖 [完整文档](https://filehub1.github.io/docs)
- 🐛 [问题反馈](https://github.com/filehub1/filehub-server/issues)
- 💬 [讨论区](https://github.com/filehub1/filehub-server/discussions)

## 下一步

- [Windows 应用下载](https://github.com/filehub1/filehub-windows-app/releases)
- [Android 应用下载](https://github.com/filehub1/android/releases)
- [查看源码](https://github.com/filehub1/filehub-server)

---

**Star 支持一下** ⭐ → [GitHub](https://github.com/filehub1/filehub-server)

MIT License · 免费开源 · 持续更新