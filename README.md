# 综合代理部署脚本 (Proxy Setup Script)

基于 `sing-box` 核心构建的轻量且功能强大的服务器代理一键部署脚本 (v3.0)。支持多协议、多出站模式、云防火墙穿透 (WARP / ZeroTrust) 及多系统架构。

## 🌟 核心特性 (Features)

- **核心精简强悍**: 完全基于最新版 `sing-box`，极简配置，高性能，低内存占用。
- **丰富的协议支持**: 
  - VLESS-Reality (最新主流抗封锁)
  - VLESS-WS + TLS / VLESS-WS
  - VMess-WS + TLS / VMess-WS
  - Hysteria2 (基于 QUIC，暴力加速)
  - TUIC (基于 QUIC v3，低延迟延迟)
  - Shadowsocks-2022
- **智能出站路由分流**:
  - **直连模式**: 高速纯净，传统 VPS 首选。
  - **WARP 模式**: 隐藏 VPS 真实本机 IP，解锁流媒体等。
  - **双节点分流模式 (Dual)**: 同时部署直连与 WARP/分流。
- **完备的 WARP 客户端接管**:
  - 支持 **WARP WireGuard 原生出站**（推荐，更轻量）。
  - 支持传统 `warp-cli` 官方客户端模式 (Socks5 代理接管)。
  - 内置完整的 WARP / ZeroTrust 注册与配置向导。
- **全平台支持系统**: 自动识别 Debian、CentOS、Alpine 及其包管理器 (apt/yum/apk)。

---

## 🚀 安装与使用 (Usage)

直接在兼容的 Linux 服务器（你需要拥有 root 权限）执行本脚本。

```bash
# 下载脚本
curl -O https://raw.githubusercontent.com/YourUsername/YourRepo/main/proxy_setup.sh

# 赋予执行权限
chmod, +x proxy_setup.sh

# 运行菜单
sudo ./proxy_setup.sh
```

### 菜单选项功能

执行后，按照中文图形化交互向导进行操作：
1. **全新安装 / 重置**: 从头配置机器类型、协议与出站模式。自动生成强随机密码和 UUID。
2. **查看当前节点信息**: 获取并显示配置连接串 (支持 V2Ray / Clash / 扫码等节点格式导入)。
3. **重启服务**: 便捷重启 `sing-box` 使配置生效。
4. **卸载**: 完全干掉配置文件与程序残留。
5. **WARP 安装向导**: 如果机器 IP 被封或解锁流媒体需求，可以引导完成本机 WARP / ZeroTrust 网络接管。
6. **WARP 状态检查**: 查看本机发往 Cloudflare 所属网络的状态。
7. **知识科普**: 萌新专供，内置解释直连、CDN 与 WARP 拓扑的关系。

---

## 📖 原理解析 & 工作模式

此脚本特别适合各种类型的 VPS（包括低配或 NAT 服务器）。出站流量控制可以通过内置功能高度定制：

- **直连 (Direct)**: 你的手机 -> VPS -> 目标网站。速度最快，取决于你的 VPS IP。
- **WARP / ZeroTrust**: 你的手机 -> VPS -> Cloudflare WARP 内网 -> 目标网站。通过 Cloudflare IP 隐藏你的 VPS 并解锁地域限制。
- **CDN 中转**: 部署 WS 类协议，通过 Cloudflare CDN 加速和隐藏 VPS 入站真实 IP。

---

## 🔧 系统要求 (Requirements)
- **OS**: Debian 10+ / Ubuntu 20.04+ / CentOS 8+ / Alpine (支持 x86_64, aarch64 等架构)
- **权限**: root 权限 (`sudo -i`)
- **环境**: 至少 64MB 可用内存（得益于 sing-box 的优秀控制）。

## 📝 免责声明 (Disclaimer)

本项目及其脚本仅供学习网络、Linux 技术及系统维护交流之用。请确保符合当地法律法规前提下合理使用网络。任何滥用可能导致的服务封停，由使用者自行承担责任。
