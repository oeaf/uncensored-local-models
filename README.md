# 无审查本地模型精选库

> ⭐ **Support This Project**
>
> [![GitHub stars](https://img.shields.io/github/stars/oeaf/uncensored-local-models?style=social)](https://github.com/oeaf/uncensored-local-models)
> [![GitHub forks](https://img.shields.io/github/forks/oeaf/uncensored-local-models?style=social)](https://github.com/oeaf/uncensored-local-models)
>
> 如果这个项目对你有用，欢迎点个 ⭐ Star！你的支持是我持续更新的动力。

10 个在 Hugging Face 上下载量最高的**无审查（uncensored / abliterated）本地模型**的归类选型手册：一张对比总表、一份按硬件分档的选型指南、每个模型一页评估。名单来自 X 用户 @NFT_Chen 2026-11-08 的帖子《Hugging Face 下载量 TOP10 无审查本地 AI 模型》（[原帖](https://x.com/NFT_Chen/status/2119568276049309961)），排名顺序按帖序，数据由本库逐个复查。

**口径说明（重要）**：本库的下载量是 **HF API 实查的近 30 天下载量（2026-11-14 查）**，与原帖声称的数字口径不同、对不上——个别差距很大（如第 10 名帖称 42.2 万、实查近 30 天只有 18.9 万；第 3 名实查 500 万反而超过帖称）。每个详情页都并列标了「帖称 vs 实查」，不要把帖称数字当真实下载量。

**先说清性质**：去审查 / abliterated 模型是社区对开源基座模型的再加工，移除了原厂的安全对齐，输出不受原厂约束。**使用者自担合规与内容责任**；好处是全程本地运行、数据不出机器。下载前请确认你所在地区的法规与模型许可证允许你的用途。

## 对比总表（下载量为 HF API 实查近 30 天，2026-11-14）

| 排名（帖序） | 模型 | 类型 | 参数量 | 近30天下载（实查） | Likes | 许可证 | 量化档位概要 | 一句话点评 | 详情 |
|---|---|---|---|---|---|---|---|---|---|
| 1 | Qwen3.8-Flash-Next-GSQ-RCO-abliterated（SC117） | 多模态 | 未标明（分片大仓） | 4,119,079 | 1,001 | Apache-2.0 | 12 个 GGUF，IQ2_XS 起、分片 | 实查下载第二，但低量化也要分片，新手先绕开 | [详情](models/01-qwen3.8-flash-next.md) |
| 2 | Huihui-Qwen3.8-27B-abliterated（huihui-ai） | 多模态 | 27B | 4,094,475 | 2,123 | Apache-2.0 | 55 个 GGUF（含 MTP 变体），档位最全 | Likes 全表第一、更新最勤，27B 级主力之选 | [详情](models/02-qwen3.8-27b.md) |
| 3 | Huihui-Qwen3.6-35B-A3B-abliterated-MTP（huihui-ai） | 多模态（MoE） | 35B-A3B | 5,004,781 | 106 | Apache-2.0 | 13 个 GGUF，Q2_K–Q5_K | 实查下载第一；MoE 推理只激活约 3B，跑得动比看起来轻松 | [详情](models/03-qwen3.6-35b-a3b.md) |
| 4 | Qwen3.5-9B-The-Defiant-Fable-Heretic（DavidAU） | 多模态 | 9B | 2,139,868 | 1,755 | Apache-2.0 | 28 个 GGUF，IQ2_M 起、imatrix | 9B 级人气王，16GB 机器的甜点档 | [详情](models/04-qwen3.5-9b-defiant.md) |
| 5 | Ornith-1.5-9B-uncensored（mradermacher） | 语言 | 9B | 1,704,579 | 280 | Apache-2.0 | 14 个 GGUF | mradermacher 的量化仓，档位齐、口碑稳 | [详情](models/05-ornith-1.5-9b.md) |
| 6 | Gemma-4-E4B-Uncensored-Aggressive（HauhauCS） | 多模态 | E4B（名称标称） | 592,837 | 1,591 | Gemma（非 Apache） | 12 个 GGUF | 小个子高人气，但许可证要单独细看 | [详情](models/06-gemma-4-e4b.md) |
| 7 | Qwen-Image-2.1-Turbo-Uncensored（AtomicChat） | 图像生成 | 未标明 | 634,156 | 817 | Apache-2.0 | 9 个 GGUF，Q2_K–Q5_K | 全表唯一的生图模型，不做对话 | [详情](models/07-qwen-image-2.1-turbo.md) |
| 8 | Gemma4-12B-QAT-Uncensored-Balanced（HauhauCS） | 多模态 | 12B | 734,910 | 571 | Gemma（非 Apache） | QAT，仅 Q4_K_M 一档（+mmproj+mtp） | 档位没得选，用 QAT 换同体积下的质量 | [详情](models/08-gemma4-12b-qat.md) |
| 9 | Qwen3-VL-8B-Instruct-abliterated（mradermacher） | 视觉语言（VL） | 8B | 519,241 | 25 | Apache-2.0 | 14 个 GGUF | 专职看图说话，Likes 低但需求对口就值 | [详情](models/09-qwen3-vl-8b.md) |
| 10 | DeepSeek-V4.1-Flash-1017-Uncensored（AtomicChat） | 语言 | 超大（总参未标明） | 189,334 | 650 | MIT | 12 个 GGUF，最低 IQ1_M 就要 4 分片 | 普通机器玩不了，看个热闹 | [详情](models/10-deepseek-v4.1-flash.md) |

## 按硬件选型指南

先说估算口径：GGUF 文件体积 ≈ 参数量 × 每参数字节数（Q4_K 约 0.55–0.6 字节、IQ2_M 约 0.35 字节、Q5_K 约 0.7 字节），运行时还要再留 KV 缓存与系统开销，下面各档的文件体积都是**估算**，下单前以原页文件列表为准。

### 16GB 内存（Mac mini 基础版 / 轻薄本）

- 主力选 **9B 级 Q4_K_M**：第 4 名 Heretic 9B（约 5.6GB）或第 5 名 Ornith 9B，质量和体积平衡最好。
- 第 6 名 Gemma-4-E4B 更小，塞得更轻松，但许可证是 Gemma 不是 Apache。
- 硬要上 27B：第 2 名的 **IQ2_M 档约 10.6GB** 能挤进 16GB，但量化损失明显、速度慢，只适合尝鲜，不适合当主力。
- 第 9 名 Qwen3-VL 8B 的 Q4 档也能跑，适合要看图说话的。

### 32GB 内存 / 24GB 显存

- **27B 的 Q4/Q5 档**是这一档的正菜：第 2 名 Qwen3.8-27B Q4_K_M 约 16.8GB、Q5 约 19–20GB（估算）。
- 第 3 名 35B-A3B 的低档（Q2_K/Q3_K，估算约 13–17GB）也能进；它是 MoE，权重全量要装下，但每 token 只激活约 3B，速度比同体积稠密模型快。

### 64GB 内存以上

- 第 3 名 35B-A3B 的高档（Q5_K，估算约 25GB）、第 2 名 27B 的 Q6/Q8 档随便挑。
- 第 1 名 Qwen3.8-Flash-Next 在这一档才有讨论意义：参数量未标明、低量化就已分片，先看原页文件总大小再决定。

### 玩不了档

- 第 10 名 **DeepSeek-V4.1-Flash**：最低的 IQ1_M（约 1.5 bit 极端量化）就已经是 4 个分片，总参数量未标明但体量摆在那里。普通家用机器要么装不下、要么慢到不可用，别惦记；真想玩 DeepSeek 系，本地小模型另找蒸馏版。

### 按需求补一句

- **要生图**：只有第 7 名 Qwen-Image 2.1 Turbo，它是 text-to-image，不做对话，别下错。
- **要看图说话（VL）**：第 9 名 Qwen3-VL 8B 是专职款；第 2/3/4/6/8 名本身也都是多模态，聊天带图一并能处理。

## 怎么跑

这 10 个全是 GGUF 格式，通用跑法就三条，无需逐个装环境：

- [Ollama](https://ollama.com)：命令行一行拉起，适合长期挂着当本地 API。
- [LM Studio](https://lmstudio.ai)：图形界面，搜模型、下量化档、点运行，适合新手和对比试档。
- [llama.cpp](https://github.com/ggml-org/llama.cpp)：最底层的官方实现，参数最全，适合折腾党。

多模态款注意要连同 mmproj 文件一起下（LM Studio 会自动提示，Ollama/llama.cpp 需手动对应）；MoE 款（第 3 名）记得选带 MTP 的文件时用支持的运行时版本。

## 每个模型一页

- [01 · Qwen3.8-Flash-Next（SC117）](models/01-qwen3.8-flash-next.md) —— 实查下载第二的分片大仓
- [02 · Huihui-Qwen3.8-27B](models/02-qwen3.8-27b.md) —— Likes 第一的 27B 主力
- [03 · Huihui-Qwen3.6-35B-A3B](models/03-qwen3.6-35b-a3b.md) —— 实查下载第一的 MoE
- [04 · Qwen3.5-9B-Defiant-Heretic（DavidAU）](models/04-qwen3.5-9b-defiant.md) —— 9B 级人气王
- [05 · Ornith-1.5-9B（mradermacher）](models/05-ornith-1.5-9b.md) —— 稳妥的 9B 量化仓
- [06 · Gemma-4-E4B-Aggressive（HauhauCS）](models/06-gemma-4-e4b.md) —— 小个子高人气
- [07 · Qwen-Image-2.1-Turbo（AtomicChat）](models/07-qwen-image-2.1-turbo.md) —— 唯一的生图款
- [08 · Gemma4-12B-QAT-Balanced（HauhauCS）](models/08-gemma4-12b-qat.md) —— QAT 只有一档
- [09 · Qwen3-VL-8B（mradermacher）](models/09-qwen3-vl-8b.md) —— 专职视觉语言
- [10 · DeepSeek-V4.1-Flash（AtomicChat）](models/10-deepseek-v4.1-flash.md) —— 普通机器玩不了

## 备注

- 本库第 2 名 huihui 的 Qwen3.8-27B 与 awesome-skills 里原单条收录的「Qwen3.8-27B-Uncensored」是**同一个模型仓**，那边是单条索引、这边是归类页，不要重复计数。
- 数据时点 2026-11-14：下载量、Likes、文件数都会变，选型时以 HF 原页当前状态为准。
- 「abliterated / heretic」指用消融等手段移除基座模型的拒答倾向，不等于模型能力变强；同名不同作者的再加工质量参差，认准上表链接里的作者仓。

## License

本库的整理文字为 MIT；各模型自身的许可证见对比总表与各自详情页，以 HF 原页为准。
