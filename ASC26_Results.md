# ASC26 — 评测结果模板

请把本文件作为提交评测结果的主文档。每次实验请补充对应字段并附上必要的脚本/日志（或将日志放在附件并在本文件中给出路径）。

## 1. 概要

- 提交人：
- 日期：
- 机器（简要）：（例如：AWS p4d, 本地 AMD/Intel + GPU/CPU 详情）

## 2. 环境与依赖

- 操作系统：
- Python：
- 关键依赖与版本（示例）：
  - torch: 
  - transformers: 
  - lm-eval (或使用的Benchmark库): 
  - nano-vllm 版本/commit: 

备注：建议提供完整的 pip freeze 或者 `pyproject.toml` / `requirements.txt` 快照。

## 3. 模型与权重

列出评测中用到的模型与权重链接：

- `Mini-Mixtral` — 权重：[`Mini-Mixtral-v0.2`](https://huggingface.co/NeuralNovel/Mini-Mixtral-v0.2)
- `Mistral-7B` — 权重：[`Mistral-7B-v0.2`](https://huggingface.co/unsloth/mistral-7b-v0.2)
- `Qwen3` — 权重：[`Qwen3-8B`](https://huggingface.co/Qwen/Qwen3-8B)（基准）

说明：若使用本地缓存或私有路径，请标注对应路径或上传方式。

## 4. 数据集

- GSM8K（版本/预处理说明）
- MBPP（版本/预处理说明）

提供下载/处理脚本与数据子集说明。

## 5. Benchmark 脚本与运行命令

示例命令（替换为你的脚本与参数）：

```bash
# 启动示例：
python run_benchmark.py --model mini-mixtral --device cuda --batch_size 1 --dataset gsm8k --output results/mini_gsm8k.json
```

请附上：运行脚本、关键参数说明、随机种子、并发/进程配置等。

## 6. 指标与结果表

在此处填写每组实验的关键度量（示例表格）：

| 模型 | 数据集 | 准确率 / 通过率 | 平均延迟 (ms) | 吞吐 (tokens/s) | 备注 |
|---|---:|---:|---:|---:|---|
| `Qwen3` | GSM8K |  |  |  | 基准 |
| `Mini-Mixtral` | GSM8K |  |  |  |  |
| `Mistral-7B` | GSM8K |  |  |  |  |
| `Qwen3` | MBPP |  |  |  |  |
| `Mini-Mixtral` | MBPP |  |  |  |  |
| `Mistral-7B` | MBPP |  |  |  |  |

请在备注中说明测量方法（暖身步数、样本数量、是否采样或贪婪解码等）。

## 7. 日志与原始输出

将重要的日志/错误输出与完整的 benchmark 日志放在附件目录或给出路径。

## 8. 结论与讨论

- 结论摘要：比较性能、准确性与资源占用
- 优化点与下一步计划

## 9. 附件与脚本

- 路径或链接：

---

填写完成后，请将本文件随仓库一并提交，或按照比赛要求提交压缩包/链接。
