# 📊 Scores In-Depth: 4-Level Comparative Matrix (Max Score: 36)

---

Scores are out of 3 points for each prompt, with 3 being a perfect adherence to all constraints and correctness checks.

| Prompt ID & Skill Tested | Success Criteria (3 Points) | GPT-OSS:20B | Llama 3 8B | DeepSeek 33B | Qwen 14B |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Level 1 Total Score** | | **6 / 9** | **5 / 9** | **1 / 9** | **3 / 9** |
| 1.1: Translation w/ No 'A' | Correct translation, NO 'A' or 'a'. | 3/3 | 1/3 (Contained 'a') | 0/3 (Contained 'a') | 0/3 (Contained 'a') |
| 1.2: Complex Formatting | 3 distinct structures (Num, Bullet, Table). | 1/3 (Failed Table/Bullet) | 1/3 (Failed separation/Table) | 1/3 (Failed all formats) | 0/3 (Failed all formats) |
| 1.3: Roman Numeral Logic | Correct CLXXVIII & CLXXX. | 2/3 (Incorrect before) | 3/3 (Perfect) | 0/3 (Math Error) | 3/3 (Perfect) |
| **Level 2 Total Score** | | **9 / 9** | **4 / 9** | **4 / 9** | **7 / 9** |
| 2.1: Logic Deduction (Switches) | Full Heat-Based Solution. | 3/3 (Perfect) | 3/3 (Perfect) | 1/3 (Flawed Multi-Step Logic) | 3/3 (Perfect) |
| 2.2: Advanced Code (Deep Path) | Functional recursive Python. | 3/3 (Perfect) | 0/3 (Broken Logic) | 3/3 (Perfect) | 3/3 (Perfect) |
| 2.3: Role-Play (Memo) | Tone, Persuasion, 200-250 word count. | 3/3 (Perfect) | 1/3 (Over Word Count) | 0/3 (Over Word Count) | 1/3 (Over Word Count) |
| **Level 3 Total Score** | | **9 / 9** | **4 / 9** | **4 / 9** | **8 / 9** |
| 3.1: Technical Design (SQL) | Valid 4-table schema w/ FKs. | 3/3 (Perfect) | 2/3 (Weak data types/PKs) | 2/3 (Non-standard SQL) | 3/3 (Perfect) |
| 3.2: Complex Math (Area) | Correct $4\pi \text{ cm}^2$ & perfect logic. | 3/3 (Perfect) | 0/3 (Conceptual Error) | 0/3 (Conceptual Error) | 3/3 (Perfect) |
| 3.3: Context/Trick (Single Number) | Correct number, single number only. | 3/3 (Perfect) | 2/3 (Failed "single number") | 2/3 (Failed "single number") | 1/3 (Incorrect calculation) |
| **Level 4 Total Score** | | **7 / 9** | **3 / 9** | **7 / 9** | **7 / 9** |
| 4.1: Network Subnetting | Correct /26, /27, /28 allocation. | 3/3 (Perfec) | 0/3 (Calculation Error) | 3/3 (Perfect) | 3/3 (Perfect) |
| 4.2: Vulnerability (XSS) | Diff + Primary Mitigation for both. | 3/3 (Perfect) | 2/3 (Weak mitigation for Stored) | 2/3 (Weak mitigation for Stored) | 2/3 (Weak mitigation for Stored) |
| 4.3: Port Scanner Script | Pseudocode, `socket`, Specific Firewall Reason. | 2/3 (Generic Firewall Reason) | 1/3 (Flawed Code/Generic Reason) | 2/3 (Generic Firewall Reason) | 2/3 (Generic Firewall Reason) |
| **GRAND TOTAL SCORE** | **Max 36** | **34 / 36** | **16 / 36** | **16 / 36** | **25 / 36** |

## Quick Take‑Away

* GPT‑OSS:20B leads with 31/36, excelling in logic and technical design but falters on formatting.
* Qwen 14B scores 25/36, strong in math & SQL but weaker on network tasks.
* Llama 3 8B and DeepSeek 33B both land at 16/36, highlighting the trade‑off between size and precision on Apple M3 hardware.
