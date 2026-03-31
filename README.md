# Mobile LLM Benchmarking Suite

A comprehensive evaluation of Small Language Models (SLMs) running locally on mobile hardware. This project compares **SmolLM (360M)**, **Qwen2 (0.5B)**, and **Phi-3.5-mini (3.8B)** across four technical domains: General Knowledge, Python Coding, Math Reasoning, and Science Logic.

## Environment and Hardware
* **Tester**: Tathagata Mitra
* **Device**: POCO F1 (M1805E10A)
* **Processor**: Octa-core Max 2.8GHz (Snapdragon 845)
* **RAM**: 6.00 GB
* **OS**: Android 8.1.0 (MIUI Global 10.0)
* **Platform**: Android via [PocketPal AI](https://github.com/a-ghorbani/pocketpal-ai)
* **Model Format**: GGUF (Quantization: Q4_K_M / Q8_0)

---

## Methodology

This benchmark utilizes an **"LLM-as-a-Judge"** framework to ensure consistent and objective scoring across different models.

1.  **Inference**: Each model was prompted with 20 targeted questions (5 per category) within the PocketPal AI mobile environment.
2.  **Evaluation**: The raw outputs were judged by **Gemini 3.1 Pro**.
3.  **Scoring**: Gemini evaluated responses based on the specific technical `evaluation_criteria` defined in the project data files.
4.  **UX Evaluation**: Beyond accuracy, a comparative UX analysis was performed using physical hardware to measure latency, thermal stability, and RAM usage on a 6GB device.

---

## Results and Analysis

### Overall Performance
This chart represents the weighted average of performance across all benchmarking categories.

![Overall Performance](./Results/Histogram_plots/Overall_performance.png)

### Category Breakdowns

| General Knowledge | Python Coding |
| :---: | :---: |
| ![General Knowledge](./Results/Histogram_plots/General_knowledge.png) | ![Python Coding](./Results/Histogram_plots/Python_coding.png) |

| Math Reasoning | Science Logic |
| :---: | :---: |
| ![Math Reasoning](./Results/Histogram_plots/Math_reasoning.png) | ![Science Logic](./Results/Histogram_plots/Science_Logic.png) |

---

## Repository Structure

* **Data/**: Contains the ground-truth prompts in JSON format.
* **Results/Histogram_plots/**: High-resolution histograms generated from the benchmarking data.
* **Results/Output/output_responses/**:Responses containing the output responses from each model.

---

## How to Reproduce

1.  **Install PocketPal AI** on your Android device.
2.  **Download the models** in GGUF format (SmolLM-360M-Instruct, Qwen2-0.5B-Instruct, Phi-3.5-mini-instruct).
3.  **Run the Prompts**: Input the specific prompts located in the `Data/` directory.
4.  **Grade the Output**: Use Gemini 3.1 Pro to score the model's response against the provided `evaluation_criteria`.

---

## About the Author
I am a second-year undergraduate physics student at Jadavpur University. My academic work focuses on computational physics and numerical methods.

* **Current Focus**: Researching AST-to-LLVM IR translation and exploring local AI agents.
* **GitHub**: [tmdeveloper007](https://github.com/tmdeveloper007)