# MaaResourceSync

适用于Windows平台的MAA资源增量更新脚本，基于 Git `SSH Fetch` 方案。

[MaaResources镜像仓库](https://github.com/Atlantis-Gura/MaaResourceMirror) | [下载地址](https://github.com/Atlantis-Gura/MaaResourceSync/releases)

## 功能特点

- 自动重试：同步失败时自动重试（最多3次，间隔10秒，可配置）
- 智能同步：增量更新，仅同步变更的资源文件
- 自动启动：资源同步完成后自动启动MAA
- 状态提示：使用 [O]/[X] 符号清晰显示操作状态

## 使用说明

1. 将压缩包内的`MaaResourceSync`文件夹放置在MAA目录下（与MAA.exe同级）
2. 按需修改`config.bat`中的设置
3. 运行`MaaResourceSync.bat`即可自动完成资源同步并启动MAA

目录结构示例：
```text
MAA/
  ├── MAA.exe
  ├── ... （MAA目录下的其他文件）
  └── MaaResourceSync/
      ├── MaaResourceSync.bat  # 主程序
      ├── config.bat           # 配置文件
      ├── .ssh/                 # SSH相关文件
      ├── git/                 # Git相关文件
      └── .git/               # Git仓库（首次运行后自动生成）
```

## 常见问题

### 这个工具有什么用
用于更新`MAA`自动战斗等功能所需的资源。更新完成后会自动启动MAA程序。

### 资源下载速度慢
如果下载速度过慢（`≤100KB/s`），脚本会自动进行重试。
您也可以手动关闭脚本重新运行。

### 提示"未找到MAA程序"
请确保将MaaResourceSync文件夹放在正确位置（与MAA.exe同级目录）。

### 其它问题
请提交 [Issue](https://github.com/Atlantis-Gura/MaaResourceSync/issues)

## 自定义更新源
如果您想从自己的仓库拉取更新，需要：

1. 生成SSH公钥并添加到您仓库的`Deploy keys`列表中
2. 修改`config.bat`中的仓库地址：
```batch
set "GIT_REMOTE=git@github.com:你的用户名/你的仓库"
```

## 更新日志

### v1.1.0
- 优化目录结构，Git相关文件统一管理
- 添加自动重试机制，提升同步稳定性
- 配置文件分离，便于管理
- 添加自动启动MAA功能
- 改进界面显示，添加清晰的状态提示
