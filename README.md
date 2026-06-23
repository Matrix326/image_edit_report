# Instruction-Guided Image Editing 技术报告

本仓库用于维护生成式人工智能课程大作业报告，主题为指令式图像编辑（Instruction-Guided Image Editing）。报告围绕“输入原图与自然语言编辑指令，输出编辑后图像，并尽量保持非编辑区域不变”这一任务展开，系统复现并分析 InstructPix2Pix、Qwen-Image-Edit 与 EditAR 三类代表性基线，并整理小组在 Qwen 低步数蒸馏、Qwen2511 微调、InstructPix2Pix 推理优化、图层分解与 EditAR 局限分析等方向的改进尝试。

## 报告内容

报告主文件为 `report.tex`，当前结构包括：

- `Introduction`：介绍指令式图像编辑任务、评测目标与整体研究路线。
- `Related Work`：综述扩散模型、多模态大模型、自回归视觉生成与图像编辑评测基准。
- `Baseline Reproduction`：复现 InstructPix2Pix、Qwen-Image-Edit 与 EditAR，并比较 SSIM、PSNR、BG-SSIM、Edit-Region Change 与 CLIP Score 等指标。
- `Method Improvement`：整理 Qwen 低步数蒸馏、Qwen2511 GT/MTP/MoE 微调、InstructPix2Pix 推理优化、图层分解与 EditAR 局限分析。
- `Performance Optimization`：汇总不同方法在速度、稳定性、背景保持与局部编辑控制方面的优化方向。
- `Conclusion`：总结基线差异、方法改进与后续研究方向。

## 目录结构

```text
.
├── report.tex                              # LaTeX 主报告文件
├── figures/                                # 报告插图与可视化结果
├── tables/                                 # 指标表格与补充表格
├── 10_06_image_edit_指令式图像编辑.pptx      # 小组汇报课件
├── build/                                  # 本地编译输出目录，不纳入版本控制
├── README.md                               # 项目说明
└── .gitignore                              # Git 忽略规则
```

## 编译方式

本报告使用中文 LaTeX 模板，建议使用 XeLaTeX 编译。确保本地已安装 TeX Live 或 MacTeX，并支持 `latexmk`。

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build report.tex
```

编译完成后，最终报告位于：

```text
build/report.pdf
```

如需清理旧编译产物并重新生成：

```bash
latexmk -C -outdir=build report.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir=build report.tex
```

## 协作流程

1. 同步主分支：

```bash
git checkout main
git pull origin main
```

2. 为自己的修改创建分支：

```bash
git checkout -b name/task
```

3. 修改 `report.tex`、`figures/` 或相关表格后提交：

```bash
git add report.tex figures/ tables/
git commit -m "Update xxx section"
git push -u origin name/task
```

4. 在 GitHub 上创建 Pull Request，经小组确认后合并到 `main`。

## 编辑规范

- 正文统一使用正式中文技术报告风格。
- 图表文件统一放入 `figures/` 或 `tables/`。
- 新增图片后应确认 `report.tex` 中的路径、编号和图注正确。
- 编译产物、临时文件和本地参考 PDF 不提交到仓库。
- 合并前建议至少运行一次完整编译，确认 `build/report.pdf` 可以正常生成。

## 当前状态

报告已完成主体结构整理、基线复现对齐、方法改进章节扩展、参考文献补全与基础排版优化。后续主要工作是进一步补充各成员负责部分的实验细节、定量表格、失败案例与最终检查。
