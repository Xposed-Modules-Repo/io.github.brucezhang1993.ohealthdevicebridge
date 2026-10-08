# OHealth Device Bridge

让 OPPO 健康连接更多第三方健康设备的 Xposed 模块。目前支持在 OPPO 健康中添加和使用薄荷健康 B1 智能体脂秤（蚂蚁阿福联名款）。

## 功能

- 在 OPPO 健康的「添加设备 → 体脂秤」中显示支持的设备，并通过蓝牙搜索、配对。
- 在 OPPO 健康中查看实时体重，完成测量后确认并保存记录。
- 有效测量时，通过 OPPO 健康查看体脂等身体成分数据；具体指标以应用显示为准。
- 连接后读取秤内保存的历史测量记录，交由 OPPO 健康认领、保存。
- 按 OPPO 健康账号分别记住已绑定设备，支持解绑。

## 支持的设备

| 设备 | 型号 |
| --- | --- |
| 薄荷健康 B1 智能体脂秤（蚂蚁阿福联名款） | AFU-BH-TZ-B1 |

目前仅适配上述型号，其他薄荷健康体脂秤及其他品牌设备尚未适配。

## OPPO 健康测试版本

| 应用 | 版本 | 测试情况 |
| --- | --- | --- |
| OPPO 健康 | 6.9.37_a7d98c1_260920 | 已完成适配检查和本地测试，真机测试待完成 |

蓝牙连接、测量保存和账号云同步仍需真机确认。其他 OPPO 健康版本尚未验证，升级应用后可能需要等待模块适配。

## 使用条件

- Android 8.0 或更高版本。
- 已安装并启用支持本模块的 LSPosed / Xposed 框架。
- 已安装上述版本的 OPPO 健康，并允许其使用蓝牙及搜索附近设备所需的权限。
- 一台支持列表中的设备。

## 安装与使用

1. 从 [Releases](https://github.com/Xposed-Modules-Repo/io.github.brucezhang1993.ohealthdevicebridge/releases) 下载并安装 APK。
2. 在 LSPosed / Xposed 管理器中启用 **OHealth Device Bridge**，确认作用应用为 **OPPO 健康**。
3. 完全退出并重新打开 OPPO 健康。
4. 打开「添加设备 → 体脂秤」，选择 **薄荷健康 B1 智能体脂秤（蚂蚁阿福联名款）**，唤醒体脂秤并按应用提示完成配对。
5. 进入设备的测量页面，按提示称重，测量完成后确认保存。

模块没有单独的操作界面，日常添加设备、测量和查看记录均在 OPPO 健康中完成。

## 问题反馈

请在 [Issues](https://github.com/Xposed-Modules-Repo/io.github.brucezhang1993.ohealthdevicebridge/issues) 中提供设备型号、手机型号、Android 版本、OPPO 健康完整版本、模块版本，以及问题出现的步骤。请勿公开账号、个人健康记录等隐私信息。

[查看源码](https://github.com/BruceZhang1993/OHealthDeviceBridge)
