# SagaFont - ColorOS 16 全局沙加体字体模块

基于 [MFGA (MakeFontsGreatAgain)](https://github.com/Numbersf/MakeFontsGreatAgain) 修改的全局字体模块，适配 ColorOS 16，将系统中英文等字体统一显示为「沙加体」。

## 需要你做的：放置沙加体字体文件

1. 将你的沙加体字体文件（单文件，含中英文全字重）重命名为：
   ```
   SagaSans.ttf
   ```
2. 放入本模块目录：
   ```
   system/fonts/SagaSans.ttf
   ```

放置完成后即可打包刷入。

> 可选优化：模块自带的旧主字体文件 `system/fonts/200.ttf`、`300.ttf`、`400.ttf`、`700.ttf`（合计约 100MB）已被配置为不再引用，可删除以减小模块体积；删除不影响沙加体显示。

## 使用前检查（重要）

- 本模块基于 MFGA，在 ColorOS 上获得最佳效果需要 **在系统设置-字体 中启用 Roboto**。
- 需要 Magisk 28.0+ 或 KernelSU 11986+。
- 若已安装旧版 MFGA 模块，请先卸载（模块 ID 不同，不会自动覆盖）。

## 修改说明

- `fonts.xml`：主字体族（sans-serif、serif、默认 fallback、zh-Hans/zh-Hant/ja/ko）全部引用 `SagaSans.ttf`，中英文统一显示为沙加体；其余 Unicode 覆盖字体（emoji、符号等）保留原逻辑。
- `fonts_list.yaml`：保留 ColorOS 的 `fonts_customization.xml` 黑名单，维持 ColorOS 字体配置兼容。
- `module.prop`：更新模块 ID/名称/描述为 SagaFont。
- `recolor_glyph.sh` / WebUI：主字体上色、屏蔽保护同步改为 `SagaSans.ttf`。
