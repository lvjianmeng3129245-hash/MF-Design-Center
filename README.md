# MF-Design Center

面向设计工作的桌面效率工具：提示词管理、截图与贴图、思维导图、桌面便签与提醒。

本仓库用于分发安装包、记录版本变化和提供在线更新信息。软件源码及个人资料不在本仓库公开。

## 下载

**当前分发版本：1.1.0-beta.43（测试版）**

| 平台 | 下载 | 状态 |
| --- | --- | --- |
| Windows x64 安装版 | [下载安装程序](https://github.com/lvjianmeng3129245-hash/MF-Design-Center/releases/download/v1.1.0-beta.43/MF-Design-Center-1.1.0-beta.43-win-x64.exe) | 推荐 |
| Windows x64 ZIP 版 | [下载安装目录 ZIP](https://github.com/lvjianmeng3129245-hash/MF-Design-Center/releases/download/v1.1.0-beta.43/MF-Design-Center-1.1.0-beta.43-win-x64.zip) | 解压完整目录后运行 |
| macOS | 暂无安装包 | 后续提供并验证后发布 |

[全部版本与更新说明](https://github.com/lvjianmeng3129245-hash/MF-Design-Center/releases) · [文件 SHA-256 校验值](https://github.com/lvjianmeng3129245-hash/MF-Design-Center/releases/download/v1.1.0-beta.43/SHA256SUMS.txt)

请下载 Release 附件中的 `.exe` 或 Windows ZIP。GitHub 自动生成的 `Source code (zip/tar.gz)` 只包含本仓库说明文件，不是软件安装包。测试版请从上方指定链接或“全部版本”下载。

## beta.43 新增主题风格

安装后点击左下角“主题风格”，开启开关并选择：**薄荷清透、珠光漫彩、轻盈橙白、晶透琉璃或自定义**。自定义默认薄荷绿＋柔雾粉，可调两种颜色、渐变方向、透明度与模糊程度。

调节即时预览，点击“应用”保存；每套参数独立记忆。首次升级保持原皮肤，关闭新主题即可恢复原来的外观。软件内图文指南已补充实际截图和切换演示。

## 主要功能

- **提示词资料库**：分组、标签、搜索、复制、收藏与备份。
- **截图与贴图**：区域截图、长截图、标注、独立贴图及区域录制。
- **思维导图**：独立导图管理、布局、编辑及导出。
- **桌面便签**：多张便签、待办、提醒与置顶。
- **更新提醒**：检查公开 GitHub Releases，查看更新内容并下载安装包。

日常资料保存在本机；检查更新需要联网。更新检测不需要 GitHub 账号或 API Key。

## 安装与升级

1. 首次使用 Windows 安装程序，按安装向导完成安装；ZIP 版需要完整解压后运行 `MF-Design Center.exe`。
2. 升级前在“设置与备份”导出完整备份。
3. 从系统托盘退出旧版，再运行新安装程序。软件沿用原有应用 ID 和 `%APPDATA%\MF Design` 资料目录。
4. 不要在升级过程中删除旧资料目录。

当前安装包未配置代码签名，Windows 可能显示未知发布者提示。可先使用下列命令核对文件哈希，再自行决定是否安装：

```powershell
Get-FileHash .\MF-Design-Center-1.1.0-beta.43-win-x64.exe -Algorithm SHA256
```

## 在线更新怎么使用

**beta.40 及更早版本需要先手动安装 beta.43 一次。** beta.41 起已经具备更新检查能力。

- 默认在启动约 25 秒后尝试检查；距离上次检查不足 6 小时会跳过当次启动检查，运行期间每 6 小时检查一次。
- 可在“设置与备份 → 软件更新”手动点击“检查更新”。
- 更新来源：`https://github.com/lvjianmeng3129245-hash/MF-Design-Center`。
- 当前发布的是测试版，请开启“接收测试版更新”。关闭后仅接收正式版。
- 发现更高版本后显示更新说明，可选择“稍后提醒”“跳过此版本”或“下载安装包”。
- 下载通过浏览器完成，之后需要退出软件并手动运行安装程序。当前版本不提供后台自动安装或静默重启。
- 软件完全退出或无法连接 GitHub 时不能检查更新；网络失败可稍后手动重试。

## 问题反馈

请在 [Issues](https://github.com/lvjianmeng3129245-hash/MF-Design-Center/issues) 中提供软件版本、Windows 版本、复现步骤和去除私人内容后的截图。请勿公开上传个人资料库、凭据或内部工作素材。

维护者发布流程见 [PUBLISHING.md](PUBLISHING.md)。
