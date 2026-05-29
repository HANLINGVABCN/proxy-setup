# 贡献指南 (Contributing)

欢迎提交 Issue 和 Pull Request！为了更好的维护，请遵循以下流程。

## 提交 Issue
- 请附带您运行时的终端错误日志或截图。
- 请说明所使用的 Linux 发行版及版本架构 (例如：`Debian 12 amd64`)。
- 请说明使用的是哪个具体协议产生了故障 (例如: Reality, Hysteria2)。

## 提交代码 (Pull Requests)
1. Fork 本仓库。
2. 创建您的 Feature 分支: `git checkout -b feature/AmazingFeature`。
3. 提交您的修改: `git commit -m 'Add some AmazingFeature'`。
4. 推送至您的分支: `git push origin feature/AmazingFeature`。
5. 开启一个 Pull Request。

### 代码规范
本脚本采用 `bash` 编写，如果您要修改核心逻辑，请确保：
- 代码保持尽量少的依赖，保证脚本在 Alpine 这种极端极简环境中可以顺利执行 (`sh` / `bash`)。
- 请勿破坏已有的 `trace` / 菜单结构。
- 新增函数如需中文字符串打印，统一使用脚本内置的颜色函数：`green`, `yellow`, `red`, `info`。
