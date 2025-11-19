# Benchmark of Open‑Source LLMs on Apple M3

This report evaluates **four leading LLMs**—GPT‑OSS:20B, Qwen 2.5 Coder 14B, DeepSeek Coder 33B, and Llama 3 8B Instruct—across a four‑level test suite (fidelity, reasoning, coding, security). The goal is to identify the model that best balances **speed, accuracy, and memory usage** on local Apple Silicon hardware.

## Model Sizes & Quantization (after quantization)

| Model Name           | Parameter Count | Selected Quantization | File Size |
|----------------------|-----------------|-----------------------|-----------|
| DeepSeek Coder 33B   | 33 B (Dense)    | Q3_K_M                | 16.07 GB  |
| GPT‑OSS:20B          | 21 B (MoE)      | MXFP4                 | 12.11 GB  |
| Qwen 2.5 Coder 14B   | 14 B (Dense)    | Q4_K_M                | 8.99 GB   |
| Llama 3 8B Instruct  | 8 B (Dense)     | Q8_0                  | 8.54 GB   |

> **Rationale** – Each quantization was chosen to fit within the ~18 GB usable memory of the M3 while preserving as much fidelity as possible:  
> • MXFP4 is a proprietary 4‑bit format that keeps MoE weights efficient.  
> • Q8_0 is nearly lossless for dense models, giving you speed without sacrificing accuracy on the M3.  
> • Q4_K_M balances quality and size for the 14 B model.  
> • Q3_K_M squeezes the 33 B model below the memory ceiling at the cost of a modest fidelity drop.

## Key Findings & Overall Winner
|**Model**|**Total Score (Max 36)**|**Average Score (Max 3.0)**|**Performance Summary**|
|---|---|---|---|
|**GPT-OSS:20B**|**32 / 36**|**2.67**|**DOMINANT WINNER (Fidelity):** Showed near-perfect accuracy (32/36), excelling in complex SQL/Math and achieving a perfect score on Network Subnetting. The most robust model for multi-step reasoning.|
|**Qwen 2.5 Coder 14B**|**25 / 36**|**2.08**|**Strong Specialist:** Near-perfect technical domain knowledge (Level 4 Subnetting/Code) but has poor compliance with basic formatting and creative constraints (Level 1).|
|**DeepSeek Coder 33B**|**16 / 36**|**1.33**|**Weakest Performance:** Despite being the largest, it struggled with fundamental math and logic, failing many core constraints and scoring the lowest overall.|
|**Llama 3 8B Instruct**|**16 / 36**|**1.33**|**Fastest Latency:** Failed critical reasoning and coding tasks (Level 2/3), confirming its size (8B) provides speed but lacks the necessary precision for specialized technical analysis.|

## Final Conclusion

The **GPT‑OSS:20B** model emerged as the most reliable technical LLM for high‑stakes tasks, offering the best blend of algebraic accuracy and domain fidelity. The trade‑off landscape is clear:

- **Large models (GPT‑OSS, DeepSeek)** risk memory errors but deliver higher precision.
- **Smaller, faster models (Llama 3 8B)** sacrifice reasoning depth for speed.

**Future Work**  
* Investigate 2‑bit or mixed‑precision quantizations to squeeze more capacity into the 18 GB budget.  
* Benchmark on newer Apple silicon (M4/M5) and compare Metal vs. MLX performance.  
* Expand the test suite to include *in‑context instruction following* and *adversarial prompts*.
