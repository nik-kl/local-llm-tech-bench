This report details the performance of four leading open-source LLMs on Apple M3 hardware across a four-level suite designed to test technical fidelity, complex reasoning, coding, and security domain knowledge.
## Key Findings & Overall Winner
|**Model**|**Total Score (Max 36)**|**Average Score (Max 3.0)**|**Performance Summary**|
|---|---|---|---|
|**GPT-OSS:20B**|**31 / 36**|**2.58**|**WINNER (Fidelity):** Showed maximal accuracy in complex SQL/Math and the highest adherence to multi-step reasoning constraints. Excellent technical model, but struggles with formatting and experienced a cache failure under load.|
|**Qwen 2.5 Coder 14B**|**25 / 36**|**2.08**|**Strong Specialist:** Near-perfect technical domain knowledge (Level 4 Subnetting/Code) but has poor compliance with basic formatting and creative constraints (Level 1).|
|**DeepSeek Coder 33B**|**16 / 36**|**1.33**|**Weakest Performance:** Despite being the largest, it struggled with fundamental math and logic, failing many core constraints and scoring the lowest overall.|
|**Llama 3 8B Instruct**|**16 / 36**|**1.33**|**Fastest Latency:** Failed critical reasoning and coding tasks (Level 2/3), confirming its size (8B) provides speed but lacks the necessary precision for specialized technical analysis.|
## Final Conclusion
The **GPT-OSS:20B** model emerged as the most reliable technical LLM for high-stakes tasks, demonstrating the strongest combination of algebraic and technical design fidelity. The major trade-off for all models was clear: increasing file size/complexity (GPT-OSS, DeepSeek) risks local memory errors, while prioritizing speed (Llama 3) sacrifices necessary reasoning and coding precision.