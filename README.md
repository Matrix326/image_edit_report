# image_edit_report

本仓库用于整理面向指令图像编辑任务的课程技术报告。报告围绕 MagicBrush 图像编辑任务，统一复现 InstructPix2Pix、Qwen-Image-Edit 与 EditAR 三类基线，并在 Method Improvement 部分整理 Qwen-Image-Edit-2511 的 LoRA 适配、MTP 目标构造与 MoE-Fusion Teacher 蒸馏改进。

## 目录结构

```text
.
├── report.tex              # 主报告文件，采用紧凑中文技术报告格式
├── figures/                # 报告插图与基线复现可视化
├── tables/                 # 指标表格
├── build/                  # LaTeX 编译产物，已加入 .gitignore
└── README.md
```

若根目录存在 `report.pdf` 与 `qwen2511_improve.pdf`，它们是用户提供的参考材料，不是最终编译产物；最终报告由 `report.tex` 编译生成到 `build/report.pdf`。

## 编译方式

中文内容建议使用 XeLaTeX：

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build report.tex
```

编译产物将生成在 `build/` 目录下。

## 待补充项

报告中使用灰色的 `[待补充：...]` 标记保留缺失信息，包括单位、邮箱、共同作者与部分团队分工。正式提交或归档前应补全这些占位内容。
