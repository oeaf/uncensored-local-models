# 05 · Ornith-1.5-9B-uncensored-GGUF（mradermacher）

直达：https://huggingface.co/mradermacher/Ornith-1.5-9B-uncensored-GGUF

## 基本信息

| 项 | 内容 |
|---|---|
| 作者 | mradermacher（GGUF 量化） |
| 基座线索 | Ornith-1.5-9B 的 uncensored 版（仓名标示）；原模型作者**未标明**（需查原页） |
| 类型 | 语言 |
| 参数量 | 9B |
| 许可证 | Apache-2.0 |
| 近30天下载（实查 2026-11-14） | 1,704,579 |
| Likes | 280 |
| 最后更新 | 2026-11-04 |
| GGUF | 14 个 |

## 帖称 vs 实查

| 口径 | 下载量 |
|---|---|
| 原帖声称 | 173 万 |
| HF API 实查（近30天） | 1,704,579 |

帖称与实查基本对得上。

## 适合谁 / 什么硬件

体积为**估算**（9B × 量化字节数）：

- Q4_K_M ≈ 5.5GB（估算）：16GB 内存档。
- Q5_K / Q6_K ≈ 6.5–7.5GB（估算）：同档质量更好。

mradermacher 是 HF 上量产量化仓的固定作者，档位命名规整、文件齐全，适合不想研究工艺名词、只想稳妥下一个能跑的人。

## 注意事项

- 这是第三方量化仓：去审查处理在基座/上游环节完成，mradermacher 只做 GGUF 量化转换，质量问题先分清出在哪一层。
- uncensored 版输出不受原厂对齐约束，使用自担合规责任。

## 与同表其他款对比

- 同为 9B，第 4 名 Heretic 人气和低档（imatrix）更强；这款胜在干净规整。已经在用 mradermacher 其他量化仓的人，选这款衔接成本最低。第 9 名 Qwen3-VL 也是他的仓。

[← 返回总表](../README.md)
