# image_edit_report

本仓库用于整理面向指令图像编辑任务的技术报告，主题为 Qwen-Image-Edit-2511 在 MagicBrush 数据集上的 LoRA 适配、MTP 目标构造与 MoE-Fusion Teacher 蒸馏。

## 目录结构

```text
.
├── report.tex              # 主报告文件，采用 NeurIPS 2026 兼容格式
├── neurips_2026.sty        # 本地 NeurIPS 2026 兼容样式
├── tables/                 # 指标表格
├── figures/                # 报告插图
└── README.md
```

## 编译方式

中文内容建议使用 XeLaTeX：

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build report.tex
```

编译产物将生成在 `build/` 目录下。

## 待补充项

报告中使用灰色加粗的 `[待补充：...]` 标记保留缺失信息，包括单位、邮箱、共同作者与部分团队分工。正式提交或归档前应补全这些占位内容。
