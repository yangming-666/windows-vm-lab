# Windows VM Lab

Windows 上的 Hyper-V 与 QEMU 实验环境脚本，覆盖虚拟机创建、配置、控制台、Ubuntu guest 准备和 guest 硬件信息检查。

**状态：实验工具集。** 脚本依赖本机 Windows 功能、管理员权限、虚拟化支持及用户自备镜像。仓库不包含虚拟磁盘、ISO、SSH 私钥或运行中的虚拟机。

## 选择入口

| 方案 | 适用场景 | 文档 |
|---|---|---|
| Hyper-V | Windows 自带虚拟化环境与常规 VM 配置 | [Hyper-V 指南](hyperv/README.md) |
| QEMU | 自定义虚拟设备、Ubuntu cloud guest 与硬件观测实验 | [QEMU 指南](qemu-realistic/README.md) |
| QEMU 运维 | 已创建 guest 的日常操作和排查 | [操作手册](qemu-realistic/OPERATIONS.md) |

## 开始前

```powershell
git clone https://github.com/yangming-666/windows-vm-lab.git
cd windows-vm-lab
```

1. 选择一种方案，阅读其 README 和对应 `vm.config.json`。
2. 按自己的磁盘位置、镜像和硬件容量调整配置。
3. 确认脚本是否启用 Windows 功能、重启系统、下载镜像或创建磁盘，再手动执行该步骤。
4. QEMU 提供 `Start-RealisticVM.ps1 -PrintOnly` 用于查看启动参数；它不等价于整套安装流程无副作用。

QEMU 示例配置有公开的演示账号口令。联网使用前应更换，并优先使用自己的 SSH 密钥。硬件信息评估结果用于解释虚拟设备差异，不保证与裸机无法区分。

## 验证范围

静态 PowerShell 语法检查只能证明脚本可解析。Hyper-V、WHPX、磁盘创建、系统重启及 guest 安装必须在目标机器上单独验收，不能由仓库文档检查替代。

[贡献指南](CONTRIBUTING.md) · [安全说明](SECURITY.md)

当前没有仓库级开源许可证。第三方镜像和软件遵守各自许可。
