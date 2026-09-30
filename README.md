# JinBeiChunQiuFixToolPro2 · 离线版（offline）

衿蓓春秋修复工具 Pro2 —— **离线版**。作者：酷安衿蓓。
本仓库**只发布离线版**（不含任何联网代码）；联网版尚未发布，不在本仓库内。

## 这是什么

面向 Android root shell（MT 管理器以 ROOT 运行 / 终端 `sh`）的春秋检测项修复工具，
共 52 项：修复 1–29、查看/扫描/诊断 30–39、工具 40–52。菜单项按春秋词条命名：
`修复（词条原文）`。

**离线版特征**：不下载、不上传、不检查更新、不做统计上报（`curl`/`wget` 零调用）；
只在本机写一个「运行次数」计数文件。

## 使用方法

```sh
# MT 管理器：设置里勾选 ROOT → 长按本脚本 → 以 ROOT 运行
sh JinBeiChunQiuFixToolPro2-offline.sh
```

如提示无执行权限：`chmod 755 JinBeiChunQiuFixToolPro2-offline.sh`

## 校验

```sh
sha256sum JinBeiChunQiuFixToolPro2-offline.sh   # 应为 318070a8e9e2351e9c44cdf3d67c24570ef2200f0fd0a682ba0cea6e0fa024da
sh JinBeiChunQiuFixToolPro2-offline.sh --verify <上面这串>   # 用外部摘要比对
sh JinBeiChunQiuFixToolPro2-offline.sh --self-test           # 四项摘要 + 许可声明自检
```

内置摘要只能防误改 / 传输损坏 / 漏签的二次打包，**挡不住有决心的篡改者**——
真正可信的校验必须让期望摘要来自脚本之外（发布页或本 README）。

## 第三方开源许可声明（随副本保留）

本工具随副本分发以下两件 **MIT 许可**的第三方作品，其版权声明与许可声明全文
随每一份副本一并保留：

| 组件 | 作者 | 仓库 | 版权 |
|---|---|---|---|
| Inode-Hijacker v2.3.1（完整内嵌） | YiJieqwq（异界） | https://github.com/YiJieqwq/Inode-Hijacker | Copyright (c) 2026 YiJieqwq |
| 春秋检测项解决方案（改编引用） | Su xiaoming（铭鐏 / mingzun09） | https://github.com/mingzun09/Chunqiu-Detector-Problem-solution | Copyright (c) 2026 Su xiaoming |

- 完整声明：[`THIRD-PARTY-NOTICES.txt`](THIRD-PARTY-NOTICES.txt)
- 许可原文：[`LICENSES/`](LICENSES/)
- 工具内查看：菜单「工具（致谢与开源许可 · 仅显示不联网）」或
  `sh JinBeiChunQiuFixToolPro2-offline.sh --license`
- 组件 2 改编自其 `File/shamiko_Plus.sh`、`File/Found property.sh`、
  `File/Tampered Attestation Key(26)Pass.sh`、`language/answer_zh.md`；
  其中属性表与 Shamiko / MagiskHide 族常见属性集一致（社区通行做法），
  本工具**未内嵌 Shamiko（LSPosed）的代码**，Shamiko 仅作为兼容与检测对象。

**转发、二次打包、内嵌到其它项目时，请完整保留上述声明与两份许可全文。**

## 风险提示

第 9 项内置 Inode-Hijacker 属设备级 inode 交换，有卡开机 / 数据不可用风险
（仅当 `/data/local/tmp` inode > 10000 时允许，且需多重确认）；第 28 项
PID 回绕 + Zygote 重启会终止应用；属性伪装与模块隔离会影响应用认证；
删除类操作不可逆。请只用于自己的设备、先备份，风险自负。

---
本仓库仅为离线版分发用；文件名与摘要以本 README 与 `SHA256SUMS.txt` 为准。
生成日期：2026-09-30
