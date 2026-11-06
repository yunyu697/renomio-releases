# Renomio Releases

Renomio 的**公开分发仓库**：只存放 Windows 安装包与更新清单。**源代码仓库保持私有**，不在此处公开。

- **安装包**：见 [Releases](https://github.com/yunyu697/renomio-releases/releases)，当前预发布 `v1.0.0-alpha5`。
- **更新清单**：滚动 release [`updates`](https://github.com/yunyu697/renomio-releases/releases/tag/updates) 下的 `latest.json`；应用内「设置 → 检查更新」只读取这里，旧地址不再使用。
- 安装包与清单均以 minisign 签名校验为准：清单中的签名必须与随包 `.sig` 完全一致，且签名绑定的 `version:` / `file:` 必须与清单声明的版本和文件名相符；不一致会被拒绝安装。

## 下载

| 包 | 文件 |
| --- | --- |
| NSIS（推荐，可选安装范围） | `Renomio_1.0.0-alpha5_x64-setup.exe` |
| MSI（机器级单一包） | `Renomio_1.0.0-alpha5_x64_en-US.msi` |
| 批量校验 | `SHA256SUMS` |

核对（PowerShell）：

```powershell
Get-FileHash .\Renomio_1.0.0-alpha5_x64-setup.exe -Algorithm SHA256
```

两个安装包**未做代码签名**，首次运行会触发 SmartScreen；请先核对 `SHA256SUMS` 再选择「仍要运行」。

## 说明

- 数据目录为 `%APPDATA%\app.renomio.desktop`，卸载不自动删除。
- 许可证：MIT。Renomio 名称与图标不随 MIT 许可一并授权，衍生分发不得暗示官方背书。
- 本仓库只放二进制与清单，不接受 issue / PR；源码问题请通过私有仓库维护者渠道反馈。
