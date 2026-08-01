# SagaFont - ColorOS 16 全局沙加体字体模块

基于 [MFGA (MakeFontsGreatAgain)](https://github.com/Numbersf/MakeFontsGreatAgain) 修改的全局字体模块，适配 ColorOS 16，将系统中英文等字体统一显示为「沙加体」。

## 文件说明

- `SagaFont/` - 模块源码，可直接放置沙加体字体后打包刷入
- `SagaFont-1.0.0.zip` - Magisk 模块安装包（61MB）

## 使用前准备（重要）

沙加体字体文件需自行添加：

1. 将沙加体字体文件（单文件，含中英文全字重）重命名为 `SagaSans.ttf`
2. 放入 `SagaFont/system/fonts/`
3. 重新打包或刷入 `SagaFont-1.0.0.zip`（zip 内 `system/fonts/` 需包含 `SagaSans.ttf`）

> 可选优化：`SagaFont/system/fonts/` 下旧主字体已删除；如从源码打包，目录无需其他字体改动。

## 使用要求

- 在 **ColorOS 系统设置-字体** 中启用 Roboto（最佳效果）
- Magisk 28.0+ 或 KernelSU 11986+
- 若已安装旧版 MFGA 模块，请先卸载（模块 ID 不同，不会自动覆盖）

## 模块特性

- 主字体族（sans-serif、serif、默认 fallback、zh-Hans/zh-Hant/ja/ko）统一引用 `SagaSans.ttf`，中英文显示为沙加体
- 保留 ColorOS 的 `fonts_customization.xml` 黑名单配置，维持 ColorOS 字体兼容
- 保留 MFGA 的 WebUI 管理、GMS 屏蔽、Unicode 过滤、改色等附加能力
