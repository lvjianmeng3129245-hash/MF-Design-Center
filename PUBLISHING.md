# 版本发布流程

此仓库是公开分发仓库；安装包放在 GitHub Releases，Git 仓库只保存说明文档。不要提交本地资料库、源码交付 ZIP、开发日志或发布凭据。

## 每次发布

1. 在本地开发项目递增版本号并构建、测试，例如 `1.1.0-beta.47`。
2. 保留应用 ID `local.mfdesign.promptlibrary` 和原资料目录，验证安装包中的版本号及更新源。
3. 运行 `node scripts/prepare-update-release.mjs` 校验更新清单并生成 SHA-256 文件和附件名单。Windows 安装包必须保留命名 `MF-Design-Center-<版本>-win-x64.exe`。
4. 创建草稿 Release，标签为 `v<版本>`，例如 `v1.1.0-beta.47`。填写准确的更新说明。
5. 上传同一轮构建的 EXE、`latest.yml`、EXE.blockmap、Windows ZIP 和 SHA256SUMS.txt；确认附件状态为 uploaded，大小和哈希正确。为提高大文件上传稳定性，EXE 与 ZIP 可逐个上传。
6. 测试版勾选 Pre-release 后发布；正式版例如 `v1.1.0` 不勾选。
7. 用低一版本的软件和独立测试资料检查真实更新、更新说明和下载链接；同时确认当前版本不会提示自己更新。
8. 更新 README 下载链接和版本号。保留旧 Release，便于人工回退；回退前备份资料，并确认数据兼容性。

## 当前更新协议

beta.41 起的软件读取 GitHub 公开 Releases API，并筛选版本号更高、非草稿且含已上传 Windows x64 EXE 的版本。预发布版本是否参与筛选由用户设置决定。

beta.46 起的 Windows 安装版使用 electron-updater / NsisUpdater 执行下载、校验及安装。检查服务先选定 Release，再读取该标签下载目录下的 `latest.yml`；GitHub 构建对测试版也生成此文件名。只上传 EXE 会导致新版能够发现更新却无法在软件内下载，因此清单必须与安装包一起上传并核验。

下载完成后由用户点击“重启并安装”；保留现有退出保存保护，只有软件真正退出才启动安装器。beta.45 及以前需要手动安装 beta.46 一次。ZIP 版需先安装，才能支持软件内覆盖升级。不要公开源码 ZIP、内部验证应用或测试日志。

macOS 尚未分发。取得安装包后，需要验证 macOS 架构、签名/公证及客户端的平台选择逻辑，再接入更新；仅上传 DMG 不会自动完成这些工作。

官方参考：[GitHub Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)、[Releases API](https://docs.github.com/en/rest/releases/releases)。
