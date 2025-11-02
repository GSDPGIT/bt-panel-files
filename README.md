# BT-Panel开心版 纯净安装脚本

> **适用版本**: Linux Panel 11.2.0  
> **最后更新**: 2025-11-02

---

## 📖 简介

这是一个经过**深度安全审计**和优化的BT（宝塔）面板安装脚本。

### 🔒 最重要的安全保障

本项目对所有来自 `bt.sb` 的第三方代码进行了**逐行审计**，确保：
- 🛡️ **无后门风险** - 审查所有可疑代码段，确认无恶意后门或远程控制
- 🔍 **代码透明** - 所有修改开源可查，接受社区监督
- ✅ **安全可信** - 删除所有不明来源的外部调用和数据上报

### ✨ 核心特点

- ✅ **已移除广告** - 删除所有安装过程中的广告内容
- ✅ **已移除统计** - 删除所有统计跟踪代码
- ✅ **自主更新源** - 升级和修复API指向自建GitHub仓库
- ✅ **完整功能** - 保留面板所有核心功能

---

## 🚀 快速开始

### 全新安装

```bash
curl -sSO https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/install_latest.sh
bash install_latest.sh
```

**安装过程**:
1. 安装基础版本（panel6_latest.zip）
2. 自动升级到11.2.0（LinuxPanel-11.2.0.zip）
3. 配置更新源指向GitHub

### 升级现有面板

```bash
curl -sSO https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/update_panel.sh
bash update_panel.sh
```

---

## 🔧 核心修改

### 1. 清理内容

已从脚本中删除：
- ❌ 所有广告展示代码
- ❌ 数据统计上报功能
- ❌ 第三方推广链接

### 2. 更新源配置

将面板的在线更新API从官方源修改为自建GitHub仓库：

| 类型 | 原始地址 | 新地址 |
|------|---------|--------|
| 升级API | `http://api.bt.sb/api/panel/updateLinux` | `https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/version.json` |
| 下载URL | `http://io.bt.sb/install/update/` | `https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/` |
| 修复API | `https://api.bt.sb/api/panel/repair` | `https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/repair.json` |

### 3. 文件托管

所有安装包均托管在GitHub：

- `panel6_latest.zip` (基础安装包)
  - MD5: `f9a7325ce17473550b09514d6bb084b8`
  - 来源: 官方下载节点
  
- `LinuxPanel-11.2.0.zip` (升级包)
  - MD5: `fc2c713a094e418f1d5e85bc4c15b16c`
  - 来源: 官方下载节点

---

## 📦 仓库文件

```
bt-panel-files/
├── install_latest.sh          # 全新安装脚本
├── update_panel.sh            # 升级脚本
├── version.json               # 版本信息API
├── repair.json                # 修复功能API
├── panel6_latest.zip          # 基础安装包
├── LinuxPanel-11.2.0.zip      # 11.2.0升级包
└── README.md                  # 本文档
```

---

## 🔍 安装流程说明

### 为什么需要两步安装？

1. **基础安装** (`panel6_latest.zip`)
   - 这是一个完整的、最新的基础安装包
   - 包含面板运行所需的所有核心文件
   
2. **自动升级** (`LinuxPanel-11.2.0.zip`)
   - 升级包包含11.2.0版本的更新文件
   - 脚本会在基础安装后自动应用此升级
   
3. **配置更新源**
   - 修改`panelPlugin.py`中的API地址
   - 使面板的在线更新指向GitHub

---

## ⚙️ 版本信息

### version.json

GitHub仓库中的`version.json`用于面板在线更新检测：

```json
{
  "version": "11.2.0",
  "download_url": "https://raw.githubusercontent.com/GSDPGIT/bt-panel-files/main/LinuxPanel-11.2.0.zip",
  "md5": "fc2c713a094e418f1d5e85bc4c15b16c",
  "date": "2025-10-28",
  "force": false
}
```

---

## 📋 系统要求

- **操作系统**: CentOS 7+, Ubuntu 16+, Debian 9+
- **内存**: 至少 512MB
- **磁盘**: 至少 100MB 可用空间
- **Python**: 会自动安装 Python 3.7

---

## ⚠️ 注意事项

1. **面板类型**: 安装后显示为"企业版"，这是原始脚本的特性
2. **到期时间**: 面板可能显示特定的到期日期，这不影响实际使用
3. **在线更新**: 面板的"在线更新"功能会从GitHub获取更新
4. **修复功能**: 面板的"修复"功能也指向GitHub的repair.json

---

## 🛠️ 常见问题

### Q: 安装失败怎么办？
**A**: 检查网络连接，确保能访问GitHub。如果GitHub访问困难，可以使用CDN加速地址。

### Q: 升级失败提示404？
**A**: 确认GitHub仓库中有`LinuxPanel-11.2.0.zip`文件，并且URL正确。

### Q: 安装后无法访问面板？
**A**: 检查防火墙设置，确保面板端口（默认8888或随机端口）已开放。

### Q: 面板显示的到期时间是什么？
**A**: 这是原始脚本的特性，不影响面板实际功能使用。

---

## 📚 相关资源

- **GitHub仓库**: https://github.com/GSDPGIT/bt-panel-files
- **原始项目**: 基于BT Panel官方脚本修改

---

## 📝 更新日志

### V1.0 (2025-11-02)
- 移除所有广告和统计代码
- 配置更新源指向GitHub
- 托管安装包到GitHub
- 简化安装流程

---

## 🙏 致谢

感谢BT Panel官方提供的优秀面板软件。

---

## 📞 其他信息

- **作者**: Lee自用
- **用途**: 仅供学习测试使用
- **许可**: 免费开源

---

**免责声明**: 本脚本仅供学习研究使用，请勿用于商业用途。使用本脚本所产生的任何后果由使用者自行承担。
