---
license: mit
language:
- en
---
# PiCo 1B

> A 1B-parameter dense language model optimized for reasoning and knowledge tasks.
>
> Link: https://huggingface.co/ArcOffical/PiCo-1B/tree/main
>
> For clarity, our model uses the tokenizer from Qwen 2 1.5B but has been trained from scratch — it is not a fine-tuned version of Qwen 2 1.5B.

---

## 📌 Model Overview

**PiCo 1B** is a compact, high-performance language model with ~1.46 billion parameters. Despite its small size, it achieves competitive performance across reasoning, knowledge, and coding benchmarks, particularly excelling in science reasoning tasks.

---

## 📋 Model Details

| Attribute | Value |
|-----------|-------|
| **Model Size** | ~1.46B parameters |
| **Architecture** | Dense transformer (decoder-only) |
| **Context Length** | 2048 tokens |
| **Precision** | FP32 / FP16 / Safetensors |
| **License** | Open-source |

---

## 📊 Benchmark Results

PiCo 1B is evaluated against **31 open-source models** in the 1B–2B parameter range across 7 standard benchmarks.

### MMLU (Massive Multitask Language Understanding)

Measures general knowledge across 57 subjects including STEM, humanities, and social sciences.

![MMLU Benchmark](https://aka.doubaocdn.com/s/AGt01wd7E8)

**PiCo 1B Score: 53.93%** — Rank: Top 3 among 1B–2B models

---

### GSM8K (Grade School Math)

Measures mathematical reasoning with grade-school level word problems.

![GSM8K Benchmark](https://aka.doubaocdn.com/s/7as81wd7E8)

**PiCo 1B Score: 29.33%** — Rank: Top 10 among 1B–2B models

---

### ARC-Challenge (AI2 Reasoning Challenge)

Measures science reasoning with grade-level science questions (harder subset).

![ARC-Challenge Benchmark](https://aka.doubaocdn.com/s/PAwz1wd7E8)

**PiCo 1B Score: 69.2%** — 🥇 **Rank #1** among 1B–2B models

---

### ARC-Easy (AI2 Reasoning Challenge)

Measures basic science reasoning with grade-level science questions (easier subset).

![ARC-Easy Benchmark](https://aka.doubaocdn.com/s/qprH1wd7E8)

**PiCo 1B Score: 85.56%** — 🥇 **Rank #1** among 1B–2B models

---

### HellaSwag (Commonsense Reasoning)

Measures commonsense natural language inference with everyday scenarios.

![HellaSwag Benchmark](https://aka.doubaocdn.com/s/TnLS1wd7E8)

**PiCo 1B Score: 49.4%** — An area for improvement

---

### HumanEval (Code Generation)

Measures functional correctness of code generation across 164 programming problems.

![HumanEval Benchmark](https://aka.doubaocdn.com/s/NaZ91wd7E8)

**PiCo 1B Score: 39.63%** — Rank: Top 4 among 1B–2B models

---

### TruthfulQA (Truthfulness)

Measures whether the model generates truthful answers rather than mimicking common misconceptions.

![TruthfulQA Benchmark](https://aka.doubaocdn.com/s/s3lo1wd7E8)

**PiCo 1B Score: 39.3%** — Rank: Top 5 among 1B–2B models

---

## 🏆 Performance Highlights

### ✅ Strengths

- **Science Reasoning**: Best-in-class performance on ARC-Easy and ARC-Challenge
- **General Knowledge**: Top 3 on MMLU, outperforming many larger 1.5B–2B models
- **Coding Ability**: Strong HumanEval performance, competitive with models 2x its size
- **Truthfulness**: Top 5 on TruthfulQA, demonstrating reliable factual output

### 📈 Areas for Improvement

- **Commonsense Reasoning**: HellaSwag score lags behind modern 1.5B+ models
- **Mathematical Reasoning**: GSM8K performance is solid but not top-tier
- **Scale**: Further training on larger, more diverse datasets could boost all benchmarks

---

## 🚀 Usage

### Quick Start

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_name = "pico-1b"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

prompt = "Explain the theory of relativity in simple terms."
inputs = tokenizer(prompt, return_tensors="pt")
outputs = model.generate(**inputs, max_length=200)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

### Model Formats

- **Safetensors** (recommended): Secure and fast loading
- **PyTorch (FP16)**: Standard format
- **GGUF**: For local inference with llama.cpp

---

## 🏋️ Training Details

| Aspect | Description |
|--------|-------------|
| **Architecture** | Dense decoder-only transformer |
| **Optimizer** | AdamW |
| **Learning Rate** | Cosine schedule with warmup |
| **Batch Size** | Configurable per GPU setup |
| **Training Framework** | PyTorch + Hugging Face Transformers |

---

## ⚠️ Limitations

- **Small Model Size**: As a 1B-parameter model, it has inherent limitations compared to larger models (7B+) on complex reasoning tasks
- **Training Data**: Primarily trained on English text; performance on non-English languages may be limited
- **Hallucinations**: Like all LLMs, it may generate factually incorrect information
- **Context Window**: Limited to 2048 tokens by default

---

## 📝 Citation

If you use PiCo 1B in your research or projects, please cite:

```bibtex
@misc{pico1b,
  title={PiCo 1B: A Compact Language Model Optimized for Reasoning},
  author={Arc Develop Team},
  year={2026},
  howpublished={\url{https://github.com/cogentaiteam-debug/PiCo-1B}},
}
```

---

## 📄 License

This model is released under an open-source license. Please see the LICENSE file for details.

---

*Last updated: June 2026*
