**Writing Guide - Zhuang Liu Lab @ Princeton University**

*By [Zhuang Liu](https://liuzhuang13.github.io/)*

[English Version](README.md)

**相关**: [Figure Guide](https://github.com/zlab-princeton-internal/figure-guide) · [AI Paper Checking](https://github.com/zlab-princeton-internal/ai-paper-checking) · [Peer Review System](https://github.com/zlab-princeton-internal/peer-review)

> 本指南面向 [Zhuang Liu](https://liuzhuang13.github.io/) 组内成员。欢迎其他人参考或改编使用。

**好的写作能让论文的贡献更清晰地传达给学术社区。对你个人而言，好的写作有助于成果的传播，效果常常是天壤之别。你已经在项目上投入了数月的心血，花时间按照本指南提升写作质量是完全值得的。**

**1\. 请在开始写作前通读本指南，争取一次做对。**
**2\. 即使已有完整初稿，根据以往学生经验，达到所有要求至少需要 5 天的全职工作量。请认真逐条对照，尽早开始。**

# **核心原则 - 读者、核心贡献与证据**

**G.1 始终记住你是在为读者写作，不是为自己写。** 这是总的指导原则。你应该让读者感到舒适，尽可能轻松地理解论文内容。下面大部分要求都是为了这个目的。一个直接的推论：

* 不要使用专业术语或引入新术语，除非*绝对*必要。这会让读者每次都需要解码。大多数好论文只有一个新术语（如 Transformer、ResNet）。


**G.2** **务必非常清楚地说明你最重要的贡献是什么。** 要非常明确和简洁地说出来，不要让读者去猜测或解析。这通常应该能用 2-3 句话描述清楚。你不一定需要在 introduction 末尾列贡献清单，但要在 abstract 和 introduction 中以明确、有结构的方式讨论，并在其他地方多次重复/换述。


**G.3 确保你的大部分实验是支撑核心贡献的证据，而不是其他"有趣"的分析或现象。** 确保实验足够有力，能让读者信服你的核心贡献和发现。这通常意味着覆盖多种数据集/设置、与所有关键 baseline 的比较，全部都为了支撑核心 claims。


**G.4 不要 overclaim。** 我们接受"较小"的贡献，但不接受夸大的 claims。不确定时，倾向严谨。这有时意味着需要给结论加上适当的限定条件。


**G.5** 确保核心贡献部分（如方法、benchmark 构建过程或实验分析，取决于你声称的贡献是什么）的 section/subsection 有足够的篇幅和细节。毕竟这是你的核心贡献——除非你想强调你没做太多（简洁性）。


## **结构与行文（段落、章节、叙事）**

**S.1** **默认把 related work 放在 conclusion 之前**，而不是 introduction 后面。大多数情况下这样更好——可以保留从 introduction 到 method 的 motivation flow，不打断叙事。只有当你确实需要 related work 来交代读者必须先了解的背景时，才把它放在 introduction 之后；通常这些背景可以放进 introduction 里。例子参考 [ConvNeXt](https://arxiv.org/abs/2201.03545)，related work 放在了论文末尾。


**S.2** 大多数段落应为 5-8 行（不含引用）。9 行接近可接受的上限。每个段落应围绕一个要点，读者应能毫不费力地用一句话总结每个段落。做不到就拆分。段落少于 3 行则合并到其他段落。


**S.3** Abstract 不要太长。最多 15-17 行（单栏格式）。[这篇论文](https://arxiv.org/pdf/2403.08632) 只有 10 行。


**S.4** Section/subsection 标题不要太长，最多 1-4 个词。不要使用 subsubsection。如果需要写总结性的句子，写在正文开头（可以加粗），而不是作为标题。


**S.5** 现阶段不要过度压缩。在最后 *24* 小时之前不要担心 9 页限制。确保版面美观、不拥挤、阅读无压力。


**S.6** **不要在 introduction 中放方法层面的细节。** Introduction 应传达高层次的问题、动机和贡献。具体使用哪个数据版本、哪个工具、哪些超参数，属于方法部分。如果读者需要你尚未介绍的背景才能理解 intro 中的某个表述，就把它移到后面。


**S.7** **使用引人入胜的、具体的 section 标题，而非笼统的单词标签。** 像 "Analysis"、"Applications"、"Interpretability" 这样的标题模糊且不好记。如果一个 section 有核心问题或发现，就用它作标题。例如：用 "Where Is the Signal?" 代替 "Interpretability"，用 "Grounding Agent Reviews" 代替 "Applications"。问句式标题对分析 section 尤其有效。


**S.8** **Conclusion 必须超越 abstract。** 你可以简要重述关键结果，但 conclusion 必须包含 abstract 中没有的 implications、interpretation 或前瞻性讨论。仅仅复述 abstract 的 conclusion 是浪费空间。考虑使用 "Conclusion and Discussion" 作为 section 标题——这自然引导更深入的思考。


**S.9** **不要让上一节的单独一行文字溢出到下一页（"widow"）。** 通过改写把它收回来，或把更多文字推过去。


**S.10** **多展示 failure cases**，尤其是 VLM、VQA、generation 类工作。可以放 appendix，空间够也可以放正文。展示 failures 让论文更可信，也方便读者了解模型实际是什么情况——只展示成功案例的论文反而显得不可信。


## **引用与 Related Work**

**C.1** 确保所有引用精准，即引用与你所说的内容相关，且比你未引用的更相关。确保正确使用 \\citet 和 \\citep：
* **\\citep** = 引用不是句子成分。"...as shown in prior work \\citep{tong2024}" 渲染为 "...as shown in prior work (Tong et al., 2024)"
* **\\citet** = 引用是句子成分。"\\citet{tong2024} show that..." 渲染为 "Tong et al. (2024) show that..."
* 简单测试：去掉引用后句子语法仍完整，用 \\citep；去掉后句子不通，用 \\citet。

多篇引用按时间顺序排列（A et al. 2023; B et al. 2025）。


**C.2** Related work 用 **\\paragraph{}** 设置话题标题，不要用 subsection。


**C.3** 引用密度要健康——不要太多也不要太少，不要某些地方过密而其他地方过疏。


**C.4 引用格式请参考[这篇论文](https://arxiv.org/pdf/2403.08632)。**

* **会议如 CVPR、ICML，只用 4 字母缩写，不写全称。**
* **所有条目删除 page/volume 等信息。**
* **会议论文用 @inproceedings，arXiv 用 @article。**
* **检查论文是否有正式发表版本。如果有，在 .bib 中使用发表版本而非 arXiv 版本。**
* **从 Google Scholar 获取 BibTeX entry（最接近我们的格式），再按上面规则修改。避免从 arXiv 或 Semantic Scholar 直接拿——它们的格式不统一。**


**C.5** 格式不确定时，参考[这篇论文](https://arxiv.org/pdf/2403.08632)的做法。引用颜色使用柔和色调（不要红色、粉色或浅绿色）。可以使用参考论文中的蓝色——从 arXiv 下载 LaTeX 源文件。


**C.6** 确保引用和正文之间有空格。即使你已经注意了，也很容易遗漏。


**C.7** Related work 不要太长。通常 2-3 个扎实的段落（6-8 行，不含引用）就够了，4 个段落基本是上限。


**C.8** 设置合适的段落间距。段落之间不要太远也不要太近。


**C.9** 确保 \\textbf{} 段落标题的大小写格式一致。


**C.10** 确保参考文献有 60+ 条。根据话题，可能需要更多（主流领域 90+ 很常见）。


**C.11** **不要有重复的参考文献条目。这比你想象的更容易发生。**


**C.12** 确保引用了正确的论文。有时两篇论文可能同名（如 XXGPT），但它们是不同的论文。


**C.13** **确保每条引用的参考文献都真实存在。** `.bib` 文件中的每个条目必须对应一篇真实的、已发表或公开可用的论文。验证标题、作者和年份是否正确——不要依赖 LLM 生成的 bib 条目而不核实。参考文献列表中错误的作者、虚构的标题或不存在的论文是严重错误，会损害可信度。


## **语言风格与语气**

**L.1** 能缩短的词语或短语就缩短，不损失任何含义。例如：xx is a method that does .... -> xx does …


**L.2** 删除/替换任何可能暗示文本由 ChatGPT 生成的词汇，即使只是轻微暗示。例如：delve。


**L.3** 长短句混合使用。不要过度使用 "which"、"that"、"and"、"xxing"（如 highlighting、demonstrating）。这种情况下可以另起一句。


**L.4** 每个 section 内使用统一的一般现在时。Related work 部分可以选择用过去时（但一般现在时也可以）。


**L.5** 不要用客观上的好词来描述你的贡献，如 novel、critical、great。这并不会提升读者对工作的评价。可以使用 new、comprehensive 等词（如果适用）。


**L.6** 不必要时不要加粗。不必要时不要大写首字母。太多大写字母看起来很乱。例如，"-" 或 ":" 后面通常不需要大写。


**L.7** 不要使用缩写形式（isn't => is not, don't => do not）。


**L.8** 在浏览器上安装 Grammarly 扩展，并确保它在 Overleaf 上正常检查语法/拼写。


**L.9 论文中不要出现超过少量破折号（---、--、-），除非绝对必要。如果 AI 写了破折号，务必删除。**


**L.10** **不要在没有引用的情况下声称什么是 "commonly assumed" 或 "widely believed"。** 如果你写 "X is commonly assumed"，reviewer 随时可以问：谁 commonly assume 了？要么给出确立该假设的引用，要么改写以避免该说法。例如，不写 "substantially more than commonly assumed"，而写 "a substantial portion of X is recoverable"。


## **图表**

图表非常重要，所以单独有一份指南。请参考 [**Figure & Table Guide**](https://github.com/zlab-princeton-internal/figure-guide)——涵盖字体、格式、视觉风格、排版、plot 等。


## **数值与精度**

**N.1** 使用合适的精度。绝大多数情况下，81.23% 是不必要的，写 81.2% 即可。


**N.2** 数字要么放在数学环境中（$82.8$），要么不放（82.8），但要全文一致。


## **术语、缩写与一致性**

**T.1** 缩写第一次出现时必须写全称。不要假设读者知道它是什么——除非它带有对某篇特定前作的引用。


**T.2** 正确使用 "i.e."、"e.g." 的表达。


**T.3** 写作要保持一致。

* "e.g." 要么用斜体要么不用，全文统一。
* 不要交替使用短破折号和长破折号。
* 不要一处写 "GPT-5-thinking"，另一处写 "GPT-5 (thinking)"。


## **项目规范、工具与模板**

**P.1** 使用这个[模板](https://colab.research.google.com/drive/1qNRjVUKKWr_9oKR1StkBW4ojTWewuq2W?usp=sharing)制作图表。注意它使用刻度、字号、网格、图例等的方式。颜色可以更改。


**P.2** 将 Overleaf 与 Dropbox 同步（使用 Dropbox 桌面版），便于更新图片，也可在 Overleaf 宕机时作为备份。


**P.3** 使用单个 .tex 文件（不要拆分为 abstract.tex、intro.tex 等），这样 Overleaf 搜索可以覆盖整篇论文。删除所有旧的未使用的 .tex 文件，它们会让协作者困惑。


**P.4** 方法名和缩写名使用 LaTeX command，因为后续可能需要修改。


**P.5** **根目录只保留一个 `.tex` 文件，命名为 `main.tex`。** 不要在根目录散放多个 .tex 文件（如 `paper_v2.tex`、`submission_icml.tex`、`old_draft.tex`）。如果有针对不同会议的版本，只保留当前活跃版本作为 `main.tex`，旧版本本地备份后从 Overleaf 删除。


**P.6** **清理过时文件。** 旧图片、未使用的 .bib 文件、之前的投稿版本、rebuttal.tex 等应在分享或投稿前从 Overleaf 项目中移除。需要的话先本地备份再删除。


## **Appendix**

**AP.1** **对 appendix 采用与正文相同的写作和排版标准。** 本指南中的所有规则——排版、图表、格式、段落结构——同样适用。


**AP.2** **如果 appendix 较长（>5 页），在开头添加目录。** 使用 `\minitoc` 或手动列表配合 `\hyperref` 链接到各 appendix section。


**AP.3** **不要出现一页只有一个小图、上下大片空白的情况。** 与其他图合并、添加文字、或调整大小填充空间。


**AP.4** **不要在图周围有过多空白。** 图应合理调整大小和位置以自然填充页面。


**AP.5** **段落格式要统一。** 选一种风格（如加粗标题后另起一行 vs. 接在同一行），全程保持一致。


**AP.6** **Appendix 的段落不能全是 1-3 行。** 将相关内容合并为实质性段落。可以比正文短一些，但仍应是真正的段落。


**AP.7** **考虑在 section 边界使用 `\newpage` 来隔离排版影响。** 图表密集的 appendix 中移动一个图经常导致后续页面连锁排版问题。`\newpage` 可以防止这种连锁——但如果会导致前一页超过一半是空白，就不要用。


## **LLM 使用**

**G.0** 不要直接复制粘贴整段内容，只采纳建议。


**G.1** 采纳 LLM 建议时要有判断力和鉴别力。


**G.2** 将 PDF 和 .tex 文件都发给 GPT。至少使用这个 prompt："Please find all grammar/punctuation errors, typos, and inconsistencies. Go through the paper very carefully." Claude Code 和 Codex 也很擅长这个任务。


**G.3** 上述过程使用多个 LLM（GPT-Pro、GPT-Thinking、GPT-instant、Gemini-Pro、Gemini-Thinking、Gemini-Fast、Claude 等）。对于特别好的模型如 GPT-Pro，可以迭代使用（开新对话）——第 2、3 次运行会发现新问题。


**G.4** 逐段发送（包括所有 caption 和 appendix），至少使用这个 prompt："Please propose revision suggestions minimally/only when very necessary"。


**G.5** 将 PDF 和 .tex 文件都发给 GPT。复制本写作要求文档的全部内容，让模型 "check the paper carefully with this requirement document, item by item"。


## **会议投稿**

**SUB.1** 不能有任何语法/拼写错误/typo（没有借口），**包括 caption（caption 对读者非常重要，且经常有最后时刻的修改；编辑后请再次检查）**。使用 Grammarly、ChatGPT 和 Gemini 各检查一遍（如果时间允许）。


**SUB.2** 消除段落末尾只有 1-3 个词的行，通过略微压缩段落实现。


**SUB.3** 确保每个图/表放在最容易阅读的位置，考虑描述它的文字位置，通常紧接在对应实验设置的文字下方。


**SUB.4** 检查 appendix，确保没有遗漏。任何 section/subsection 不能只有一个表格/图而没有文字描述。


**SUB.5** 正文长度 *恰好* 为会议要求的 8/9 页，不多一行也不少一行。


**SUB.6** 确保 OpenReview 上的 abstract 是最新的，不要是过时版本（如注册论文时的版本）。


**SUB.7** 清除 OpenReview abstract 中的 LaTeX 内容，如 \\citet{}、\\emph{}、\\methodname{}。


**SUB.8** 清除 PDF 上作者的所有批注。


**SUB.9** 确保在截止时间前 30 分钟提交一个 8/9 页的版本到 OpenReview。


## **arXiv 投稿**

**A.1** 与合作者/PI 确认哪个论文类别（如 cs.CV、cs.ML、cs.CL）最适合作为 arXiv 上的主类别和交叉类别。


**A.2** 确保 arXiv abstract 页面与 PDF abstract 同步（后者经常有最后时刻的改动）。确保数学符号、引用和链接在 abstract 页面正常显示。


**A.3** 如果论文已被会议录用/接收，在 arXiv abstract 页面的 comment 中注明。


**A.4** 使用 Overleaf 的 "submit to arXiv" 功能。如果是第一次提交到 arXiv，请向合作者咨询。如果确实不确定，让合作者代为提交。


**A.5** 注意 arXiv 每天的提交截止时间是美东时间下午 2 点。论文会在美东时间约晚上 9 点上线并获得链接。


**A.6** **注意论文上 arXiv 后完整的 LaTeX 源码是公开可见的。** 提交前从 Overleaf 中移除所有不必要的文件、未使用的图片/PDF（如 rebuttal.tex）。删除 main.tex 中的所有 LaTeX 注释。


**A.7** 大多数论文我们都会在实验室 GitHub 和 HuggingFace 账号下发布代码和模型。详情联系 [Taiming Lu](mailto:tl0463@princeton.edu)。


**A.8** Appendix 开头使用 "\\section\*{\\Large Appendix}"。不要称之为 "supplementary materials"。


## **代码发布**

**C.1** 确保 repo 中的链接可点击，README 使用正确的 markdown 格式。


**C.2** 论文被接收后添加会议信息。


**C.3** 包含论文标题、机构、作者、arXiv 链接、license、致谢和 bib 引用。


**C.4** 在 README 主页中包含最重要代码的运行命令。


**C.5** 使用 Claude Code 优化代码文件组织、命名和 repo 命名。


**C.6** 使用 Claude Code 优化 README 结构。


## **实用 LaTeX 命令**

* 设置段落缩进：
  * "\\renewcommand{\\paragraph}\[1\]{\\vspace{1.25mm}"
* 设置颜色：
  * \\definecolor{citecolor}{HTML}{0071BC} % 引用链接
  * \\definecolor{linkcolor}{HTML}{ED1C24} % 内部链接（ref、TOC 等）
  * \\usepackage\[pagebackref=false, breaklinks=true, colorlinks,
  *             citecolor=citecolor, linkcolor=linkcolor, bookmarks=false\]{hyperref}
* URL 换行：
  * \\usepackage{url}
  * \\def\\UrlBreaks{\\do\\/\\do-}
* 作者批注
  * 例如 \\newcommand{\\ab}\[1\]{{\\color{orange}\[AB: \#1\]}}

---

## TODO

- **格式统一**：每条规则用粗体写核心要求，后跟正常字体的简短解释。示例用可折叠的 `<details>` 展示。
- **拆分复合条目**：部分条目包含多个要点，拆分为独立条目。
- **添加更多示例**：为更多规则添加正反示例（可折叠）。
- **Figure guide 独立**：将图表相关规则（F.*）移至单独的 Figure Guide 文档。
