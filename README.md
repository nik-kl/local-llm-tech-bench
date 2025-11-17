This report details the performance of four leading open-source LLMs on Apple M3 hardware across a four-level suite designed to test technical fidelity, complex reasoning, coding, and security domain knowledge.
## Model Sizes & Quantization (README)
| Model Name           | Parameter Count | Selected Quantization | File Size |
|----------------------|-----------------|-----------------------|-----------|
| GPT-OSS:20B          | 21 B (MoE)      | MXFP4                 | 12.11 GB  |
| Llama 3 8B Instruct | 8 B (Dense)     | Q8_0                  | 8.54 GB   |
| Qwen 2.5 Coder 14B   | 14 B (Dense)    | Q4_K_M                | 8.99 GB   |
| DeepSeek Coder 33B   | 33 B (Dense)    | Q3_K_M                | 16.07 GB  |

**Rationale** – Each quantization was chosen to fit within the ~18 GB usable memory of the M3 while preserving as much fidelity as possible:  
• MXFP4 is a proprietary 4‑bit format that keeps MoE weights efficient.  
• Q8_0 is nearly lossless for dense models, giving you speed without sacrificing accuracy on the M3.  
• Q4_K_M balances quality and size for the 14 B model.  
• Q3_K_M squeezes the 33 B model below the memory ceiling at the cost of a modest fidelity drop.
## Key Findings & Overall Winner
|**Model**|**Total Score (Max 36)**|**Average Score (Max 3.0)**|**Performance Summary**|
|---|---|---|---|
|**GPT-OSS:20B**|**31 / 36**|**2.58**|**WINNER (Fidelity):** Showed maximal accuracy in complex SQL/Math and the highest adherence to multi-step reasoning constraints. Excellent technical model, but struggles with formatting and experienced a cache failure under load.|
|**Qwen 2.5 Coder 14B**|**25 / 36**|**2.08**|**Strong Specialist:** Near-perfect technical domain knowledge (Level 4 Subnetting/Code) but has poor compliance with basic formatting and creative constraints (Level 1).|
|**DeepSeek Coder 33B**|**16 / 36**|**1.33**|**Weakest Performance:** Despite being the largest, it struggled with fundamental math and logic, failing many core constraints and scoring the lowest overall.|
|**Llama 3 8B Instruct**|**16 / 36**|**1.33**|**Fastest Latency:** Failed critical reasoning and coding tasks (Level 2/3), confirming its size (8B) provides speed but lacks the necessary precision for specialized technical analysis.|
## Final Conclusion
The **GPT-OSS:20B** model emerged as the most reliable technical LLM for high-stakes tasks, demonstrating the strongest combination of algebraic and technical design fidelity. The major trade-off for all models was clear: increasing file size/complexity (GPT-OSS, DeepSeek) risks local memory errors, while prioritizing speed (Llama 3) sacrifices necessary reasoning and coding precision.
