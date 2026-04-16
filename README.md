# WUST_wifi_keeper
一个轻量的抗断网武汉科技大学校园网自动认证工具

## 核心特性
* **全自动无感运行**：开机后自动隐藏至系统托盘，静默维持网络连接。
* **双层探针检测**：通过 HTTP 探针精准识别网关劫持，防 ICMP（Ping）穿透误判。
* **物理断线自愈**：当 Wi-Fi 彻底断开时，可直接调动底层网卡自动重连。
* **多校区支持**：开放 `nasId` 参数配置，兼容黄家湖/青山等不同校区网关。
* **日志记录**：内置日志查看器，随时追踪网络状态。

## 快速开始（普通用户）
1. 前往右侧的 [Releases](https://github.com/LotYC1/WUST_wifi_keeper/releases/latest) 页面下载最新版本的 `wifi_keeper.exe`。
2. 双击运行，在弹出的窗口中填入：
   * **Wi-Fi 名称** (如: `WUST-WiFi6`)
   * **学号** 和 **密码**
   * **网关 ID (nasId)**：黄家湖默认填 `2`，青山校区可通过浏览器开发者工具抓包获取。
3. 点击“保存并隐藏监控”，程序将自动最小化到右下角托盘。
4. **注意**：程序会在同级目录下生成 `wifi_config.json` 存储配置，请勿将其分享给他人。

## 源码编译（开发者用户）
如果你想基于源码自行打包，请确保已安装 Python 3.8+，并执行以下命令：

```bash
# 1. 安装依赖
pip install requests pystray pillow pyinstaller

# 2. 单文件打包 (无终端黑框，可选添加 -i icon.ico 自定义图标)
pyinstaller --noconsole --onefile wifi_keeper.py
```
编译后的可执行文件位于 dist/ 目录下。

## 免责声明
本项目仅供编程学习与交流使用，账号密码仅保存在本地，请遵守学校网络使用规范。
