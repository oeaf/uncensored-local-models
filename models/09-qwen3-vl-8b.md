# 09 · Qwen3-VL-8B-Instruct-abliterated-GGUF（mradermacher）

直达：https://huggingface.co/mradermacher/Qwen3-VL-8B-Instruct-abliterated-GGUF

## 基本信息

| 项 | 内容 |
|---|---|
| 作者 | mradermacher（GGUF 量化） |
| 基座线索 | Qwen3-VL-8B-Instruct 的 abliterated 版（仓名标示） |
| 类型 | 视觉语言（VL） |
| 参数量 | 8B |
| 许可证 | Apache-2.0 |
| 近30天下载（实查 2026-11-14） | 519,241 |
| Likes | 25（全表最低） |
| 最后更新 | 2026-10-22 |
| GGUF | 14 个 |

## 帖称 vs 实查

| 口径 | 下载量 |
|---|---|
| 原帖声称 | 66.9 万 |
| HF API 实查（近30天） | 519,241 |

帖称偏高约三成。Likes 只有 25，说明它是个小众对口工具，不是人气货——下载量主要来自真实的看图需求。

## 适合谁 / 什么硬件

体积为**估算**（8B × 量化字节数，另需 mmproj 视觉投影文件）：

- Q4 档 ≈ 5GB（估算）+ mmproj：16GB 内存可跑。
- 需求明确才下：给图片做描述/问答/OCR 式提取，且要无审查版 VL 的，这款是全表唯一专职的。

## 注意事项

- VL 模型必须主 GGUF + mmproj 配套使用，漏下 mmproj 就只能纯文本。
- 这是第三方量化仓，去审查处理在上游完成；Likes 低意味着社区反馈少，先小档验证效果再投入使用场景。
- abliterated 输出不受原厂对齐约束，使用自担合规责任。

## 与同表其他款对比

- 第 2/3/4 名也都是多模态、也能看图，但定位是「聊天为主、带图顺便」；这款是「看图为主」。纯 VL 任务选这款，聊天带图选前面几款。

[← 返回总表](../README.md)
