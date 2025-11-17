This section documents the hardware and software configuration used for all benchmark runs, ensuring the results are reproducible.

## Hardware and Software Environment

The evaluation was conducted on a high-performance consumer machine designed for local AI inference.

| Parameter                   | Specification                                         | Note                                                                                  |
| :-------------------------- | :---------------------------------------------------- | :------------------------------------------------------------------------------------ |
| **Hardware**                | **Apple M3 MacBook Air** (8 CPU Cores / 10 GPU Cores) | The unified memory architecture is leveraged by the Metal framework.                  |
| **Total Memory**            | **24 GB Unified Memory**                              | The primary bottleneck is the usable memory after system overhead.                    |
| **Application**             | **LM Studio**                                         | Used for its optimized MLX implementation on Apple Silicon.                           |
| **Inference Configuration** | **Threads:** 8 (Matches CPU count)                    | Maximizes parallelism for CPU-bound tasks.                                            |
| **GPU Offload**             | **Full (18GB available)**                             | Prioritizes maximum GPU utilization to achieve optimal Tokens Per Second (TPS) speed. |
| **Context Length**          | **4096 Tokens**                                       | A conservative setting to prevent swapping across all four model sizes.               |

### Thermal and Operational Environment (Crucial for M3 Benchmarks)

All tests were performed under controlled conditions to maximize performance and minimize thermal throttling:

* **Power:** The **MacBook Air was plugged in at all times** to ensure maximum power delivery (Performance Mode).
* **Background Activity:** **No programs were running in the background** (except macOS and the core LM Studio service) to eliminate CPU and memory contention.
* **Thermals:** The MacBook was placed on a flat surface with **no obstruction of air flow**, and **no case or sleeve was used** that could kill the thermals, ensuring heat dissipation was optimal throughout all extended Level 3 and 4 tests.
