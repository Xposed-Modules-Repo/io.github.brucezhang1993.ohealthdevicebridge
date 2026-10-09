# OHealth Device Bridge

让 OPPO 健康连接更多第三方健康设备的 Xposed 模块。目前支持薄荷健康 B1 智能体脂秤（蚂蚁阿福联名款）和小米体重／体脂秤，具体支持及验证状态见下表。

## 功能

- 在 OPPO 健康的「添加设备 → 体脂秤」中显示支持的设备，并通过蓝牙搜索、配对。
- 在 OPPO 健康中查看实时体重，完成测量后确认并保存记录。
- 有效测量时，通过 OPPO 健康查看体脂等身体成分数据；具体指标以应用显示为准。
- AFU B1 和小米一代、二代秤连接后读取秤内保存的历史测量记录，交由 OPPO 健康认领、保存。
- 按 OPPO 健康账号分别记住已绑定设备，支持解绑。

## 支持的设备

| 设备 | 型号 | 支持状态 | 验证状态 |
| --- | --- | --- | --- |
| 薄荷健康 B1 智能体脂秤（蚂蚁阿福联名款） | AFU-BH-TZ-B1 | 支持 | 已验证 |
| 小米体重秤（一代） | XIAOMI-MI-SCALE-V1 | 支持 | 未验证 |
| 小米体脂秤（二代） | XIAOMI-MI-SCALE-V2 | 支持 | 未验证 |
| 小米体脂秤 S400 | XIAOMI-S400（米家：yunmai.scales.ms103 / ms104） | 实验性支持 | 未验证 |
| 小米体脂秤 S800 | XIAOMI-S800（米家：xiaomi.scales.ms116） | 实验性支持 | 未验证 |

目前仅适配上述型号。新增小米设备尚未完成真机验证；S400／S800 的自动取钥及广播测量流程属于实验性支持，具体能力与验收步骤见[小米体脂秤接入与验收](https://github.com/BruceZhang1993/OHealthDeviceBridge/blob/1.1.0/docs/XIAOMI_ACCEPTANCE.md)。

## OPPO 健康测试版本

| 应用 | 版本 | 测试情况 |
| --- | --- | --- |
| OPPO 健康 | 6.9.37_a7d98c1_260920 | AFU B1 已验证；新增小米设备未验证 |

新增小米设备的蓝牙测量、记录保存和账号云同步仍需真机确认。其他 OPPO 健康版本尚未验证，升级应用后可能需要等待模块适配。

## 使用条件

- Android 8.0 或更高版本。
- 已安装并启用支持本模块的 LSPosed / Xposed 框架。
- 已安装上述版本的 OPPO 健康，并允许其使用蓝牙及搜索附近设备所需的权限。
- 一台支持列表中的设备。
- S400／S800 需先在米家登录并绑定设备，再单独授予本模块 root 权限；首次读取和重新获取凭证需要联网。

## 安装与使用

1. 从 [Releases](https://github.com/Xposed-Modules-Repo/io.github.brucezhang1993.ohealthdevicebridge/releases) 下载并安装 APK。
2. 在 LSPosed / Xposed 管理器中启用 **OHealth Device Bridge**，确认作用应用为 **OPPO 健康**。
3. 完全退出并重新打开 OPPO 健康。
4. 打开「添加设备 → 体脂秤」，选择对应设备，唤醒体脂秤并按应用提示完成配对。S400／S800 选择对应的“从米家读取”产品，在模块授权页授权 root 并选择已绑定的秤，再返回 OPPO 健康完成验证。
5. 进入设备的测量页面，按提示称重，测量完成后确认保存。

日常添加设备、测量和查看记录均在 OPPO 健康中完成。S400／S800 读取米家设备时会打开模块授权页，无需手动填写账号、Token 或 BLE Key；Xposed 作用域只需勾选 OPPO 健康，无需勾选米家。

## 问题反馈

请在 [Issues](https://github.com/Xposed-Modules-Repo/io.github.brucezhang1993.ohealthdevicebridge/issues) 中提供设备型号、手机型号、Android 版本、OPPO 健康完整版本、模块版本，以及问题出现的步骤。请勿公开账号、个人健康记录等隐私信息。

## 项目文档

- [技术与开发说明](https://github.com/BruceZhang1993/OHealthDeviceBridge/blob/1.1.0/docs/DEVELOPMENT.md)：适配实现、架构、构建、签名与发布流程。
- [AFU 修复与验收](https://github.com/BruceZhang1993/OHealthDeviceBridge/blob/1.1.0/docs/AFU_ACCEPTANCE.md)：本地验收记录及真机验收步骤。
- [小米体脂秤接入与验收](https://github.com/BruceZhang1993/OHealthDeviceBridge/blob/1.1.0/docs/XIAOMI_ACCEPTANCE.md)：米家授权、设备能力边界及真机验收步骤。

## 开源许可

[MIT](https://github.com/BruceZhang1993/OHealthDeviceBridge/blob/1.1.0/LICENSE) · [查看源码](https://github.com/BruceZhang1993/OHealthDeviceBridge)
