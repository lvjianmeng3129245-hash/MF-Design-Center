# 版本发布流程

此仓库是公开分发仓库；安装包放在 GitHub Releases，Git 仓库只保存说明文档。不要提交本地资料库、源码交付 ZIP、开发日志或发布凭据。

## 每次发布

1. 在本地开发项目递增版本号并构建、测试，例如 `1.1.0-beta.43`。
2. 保留应用 ID `local.mfdesign.promptlibrary` 和原资料目录，验证安装包中的版本号及更新源。
3. 生成 SHA-256 校验文件。Windows 安装包必须保留命名 `MF-Design-Center-<版本>-win-x64.exe`。
4. 创建草稿 Release，标签为 `v<版本>`，例如 `v1.1.0-beta.43`。填写准确的更新说明。
5. 上传同版本 EXE、可选的 Windows ZIP 和校验文件；确认附件状态为 uploaded，大小和哈希正确。
6. 测试版勾选 Pre-release 后发布；正式版例如 `v1.1.0` 不勾选。
7. 用低一版本的软件和独立测试资料检查真实更新、更新说明和下载链接；同时确认当前版本不会提示自己更新。
8. 更新 README 下载链接和版本号。保留旧 Release，便于人工回退；回退前备份资料，并确认数据兼容性。

## 当前更新协议

beta.41 起的软件读取 GitHub 公开 Releases API，并筛选版本号更高、非草稿且含已上传 Windows x64 EXE 的版本。预发布版本是否参与筛选由用户设置决定。

当前实现不使用 electron-updater，无需 `latest.yml`、`beta.yml` 或 `.blockmap` 才能提示更新。不要将只有 ZIP 或只有源码的 Release 当作可更新的 Windows 版本。

macOS 尚未分发。取得安装包后，需要验证 macOS 架构、签名/公证及客户端的平台选择逻辑，再接入更新；仅上传 DMG 不会自动完成这些工作。

官方参考：[GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)、[Releases API](https://docs.github.com/en/rest/releases/releases)。
