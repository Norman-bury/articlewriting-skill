# 科研写作助手 (Research Writing Assistant)

把“论文写作”从一次性聊天，升级成可追踪、可恢复、可复用的工程化协作流程。  
这个 Skill 面向本科生、研究生和早期科研人员，目标很直接：少走弯路，减少返工，把时间花在真正有价值的研究内容上。

![科研写作助手使用流程](assets/readme/workflow.png)

## 项目定位

这不是一个“只会润色句子”的提示词包，而是一套完整的科研写作协作系统。  
它会在任务开始前先对齐目标与约束，自动接管 `plan/` 项目上下文，再按学科和任务路由到对应模块执行。

如果你在做毕业论文、课程项目论文或投稿初稿，这个 Skill 会比普通对话式写作工具更稳定，因为它强调流程、记录和回写，不依赖单轮记忆。

## 核心能力

- 全流程协作：从选题推进、正文写作、图表生成到投稿前自审，按阶段门禁执行
- 去AI化写作：约束机械过渡词、空壳强调句、主观化表达和列表堆砌
- 学科化写作支持：工科、社科、医学、法学模块分流
- 文献综述支持：英文检索整合与中文文献整理协作
- 环境自动化：Miniconda 安装、虚拟环境创建、绘图依赖安装与排错
- 计划可恢复：`plan/` 持续记录目标、产出、决策和下一步动作

## 适用平台

本 Skill 采用目录化设计，适用于主流本地技能加载工作流，当前适配以下平台：

- Cursor
- Windsurf
- Antigravity
- Qoder
- CC
- OpenCode

## 你会得到什么产物

默认情况下，Skill 产物是项目内文件，不是 Word 成品文件。

| 产物类型 | 默认格式 | 说明 |
|---|---|---|
| 写作正文 | `.md` / 纯文本 / `.tex` | 便于版本管理和后续再加工 |
| 过程记录 | `plan/*.md` | 包含目标、进度、阶段门禁、偏好和决策 |
| 图表脚本 | `.py` | 可复现图表，这个需要或者自己运行，或者直接利用skill也可以帮你运行生成 |
| 提示词资产 | `.md` | 可复用的翻译、润色、去AI化模板 |

## 重要边界（务必先看）

1. Skill 默认不会自动生成或直接写入 `.docx`。  
2. Skill 默认不会替你“打开 Word 并排版”，需要你手动复制或用工具转换。  
3. Skill 可以生成适合粘贴进 Word 的纯文本段落，但最终样式（标题级别、页眉页脚、目录、参考文献域）需要你在 Word 端处理。  
4. 文献不会编造，引用需可追溯；高风险结论需要二次核验，但是数据是我们说了算，实验跑不跑随便，重点是出结果。 

## 安装

下载仓库，解压后把 `research-writing-skill/` 复制到你的论文写作目录就可以用了。

推荐步骤：

1. 下载本仓库压缩包并解压。
2. 把 `research-writing-skill/` 文件夹复制到你的论文项目目录。
3. 在你使用的平台中加载该本地 Skill 目录（或复制到平台要求的 skills 目录）。

## 真实使用案例（输入 -> 输出）

![真实使用案例：输入到输出](assets/readme/real-case-input-output.png)

## 标准协作流程（推荐）

1. 明确本轮任务目标、输出物、截止时间
2. 让 Skill 创建或读取 `plan/`
3. 让 Skill 先产出可审阅的 Markdown 正文
4. 运行风格自检脚本，处理去AI化与排版问题
5. 确认术语、数据、引用后再做终稿整理
6. 手动迁移到 Word 并完成模板排版

## 如何把 Markdown 交付到 Word

### 方案 A：手动复制（默认推荐）

1. 让 Skill 输出“纯文本段落版”正文（避免 Markdown 标记）
2. 在编辑器中复制正文并粘贴到 Word
3. 在 Word 中应用学校模板样式（标题、正文、图注、表注）
4. 手动检查公式、参考文献、图表编号与交叉引用

### 方案 B：Pandoc 转换（可选）

如果你本地已安装 Pandoc，可尝试：

```bash
pandoc draft.md -o draft.docx
```

说明：这只解决格式转换，不替代学校模板排版和最终人工校对。

## 常用脚本

- 初始化计划目录  
  macOS/Linux: `bash research-writing-skill/scripts/init_plan.sh`  
  Windows PowerShell: `powershell -ExecutionPolicy Bypass -File research-writing-skill/scripts/init_plan.ps1`

- 去AI化与排版自检  
  macOS/Linux: `bash research-writing-skill/scripts/style_check.sh <文件.md>`  
  Windows PowerShell: `powershell -ExecutionPolicy Bypass -File research-writing-skill/scripts/style_check.ps1 -FilePath <文件.md>`

## 模块地图

| 场景 | 模块 |
|---|---|
| 全流程阶段推进与投稿准备 | `modules/workflow-lifecycle.md` |
| 通用论文写作 | `modules/writing-core.md` |
| 文科/社科写作 | `modules/writing-humanities.md` |
| 医学/生物写作 | `modules/writing-medical.md` |
| 法学写作 | `modules/writing-law.md` |
| 文献综述 | `modules/literature-review.md` |
| 翻译/润色/去AI化 | `modules/prompts-collection.md` |
| 投稿前自审 | `modules/peer-review.md` |
| 统计分析 | `modules/statistical-analysis.md` |
| Python 图表 | `modules/figures-python.md` |
| 流程图/架构图提示词生成 | `modules/figures-diagram.md` |
| 环境安装与排错 | `modules/environment-setup.md` |
| LaTeX 排版 | `modules/latex-guide.md` |



## FAQ

### 为什么默认产物不是 Word？

因为科研协作更需要可追踪、可复用、可版本化的文本资产，Markdown 更适合过程迭代。Word 适合最终交付，所以放在最后一步处理更稳妥。

### 可以直接让我“生成最终可提交版本”吗？

可以做接近终稿的内容，但学校模板、目录域、页码、参考文献域、格式细节仍建议在 Word 端完成。现在市场上的工具md转docx，转pdf，都不是很好用推荐手动复制过去。我经常做的就是把段落先复制到微信聊天框，然后从微信聊天框复制到Word，这样也不用格式刷。

### 这个 Skill 会不会瞎编文献？

不会。规则层面明确禁止编造文献与数据；引用要求可追溯。

## 仓库结构

```text
research-writing-skill/
├── SKILL.md
├── modules/
│   ├── module-guide.md
│   ├── workflow-lifecycle.md
│   ├── writing-core.md
│   ├── writing-humanities.md
│   ├── writing-medical.md
│   ├── writing-law.md
│   ├── literature-review.md
│   ├── prompts-collection.md
│   ├── peer-review.md
│   ├── statistical-analysis.md
│   ├── figures-python.md
│   ├── figures-diagram.md
│   ├── environment-setup.md
│   └── latex-guide.md
├── templates/
│   ├── figure-template.py
│   ├── color-palettes.md
│   └── paper-outline.md
├── plan-template/
│   ├── project-overview.md
│   ├── stage-gates.md
│   ├── outline.md
│   ├── progress.md
│   └── notes.md
└── scripts/
    ├── init_plan.sh
    ├── init_plan.ps1
    ├── style_check.sh
    └── style_check.ps1
```

## 图片与下载说明

- README 展示图存放在 `assets/readme/`。
- 仓库包含 `.gitattributes`，已将 `assets/readme/**` 标记为 `export-ignore`，用于减少 Source code 压缩包中的图片体积。


## 版本

- 版本：1.1.0
- 更新日期：2026-03-04
