## LLM

The performance landscape of medical large language models (LLMs) is currently divided between high-performing **proprietary (closed-source)** systems and rapidly advancing **open-source (open-access)** models. While proprietary models generally lead in raw benchmark scores, open-source models are closing the gap, particularly in specialized text analysis and privacy-sensitive clinical applications.

### **1. Proprietary Models: The Performance Leaders**
Proprietary models, such as those from Google and OpenAI, typically hold the highest scores on standardized medical exams due to their massive scale and closed development pipelines.

*   **GPT-5:** Currently the top-performing model across medical benchmarks.
    *   **MedQA (USMLE):** 95.84%.
    *   **USMLE Step 2:** 97.50%.
    *   **MMLU Medical Genetics:** 100%.
    *   **MedXpertQA (Multimodal Reasoning):** 69.99% (surpassing human experts at 45.76%).
*   **Med-PaLM 2:** A leading expert-level medical model from Google.
    *   **MedQA (USMLE):** 86.5%.
    *   **PubMedQA:** 81.8%.
    *   **Human Preference:** Preferred by physicians over human physician-generated answers on 8 of 9 clinical axes.
*   **GPT-4 / GPT-4o:** High-performing generalist models used as frequent baselines.
    *   **GPT-4 (MedQA):** 86.1% (base version).
    *   **GPT-4o (MedQA):** 91.04%.
    *   **GPT-4o (Multimodal Reasoning):** 40.73%.

### **2. Open-Source Models: Transparency and Specialization**
Open-source (or open-access) models provide public weights or code, making them suitable for local deployment and institutional research.

*   **MEDITRON-70B:** An open-access model adapted from Llama-2 specifically for medical reasoning.
    *   **MedQA (4-option):** 70.2% (using Self-Consistency Chain-of-Thought).
    *   **PubMedQA:** 81.6% (comparable to Med-PaLM 2).
    *   **MedMCQA:** 66.0%.
*   **Me-LLaMA (70B-chat):** A family of open-source models trained on 129 billion medical tokens, including clinical notes.
    *   **MedQA:** 62.3% (Supervised).
    *   **Clinical Diagnosis:** Comparable to ChatGPT and GPT-4 in diagnosing complex clinical cases (NEJM cases).
    *   **Comprehensive Tasks:** Excels in Relation Extraction (RE), Named Entity Recognition (NER), and natural language inference.
*   **Other Open Baselines:**
    *   **PMC-LLaMA:** 49.2% on MedQA (4-option).
    *   **Llama-2-70B (Base):** 61.3% on MedQA (4-option).
    *   **Mistral-7B / Zephyr-7B:** 41.1% and 48.5% on MedQA, respectively.

### **Comparison Table: Benchmarks at a Glance**
| Model Type | Model Name | MedQA (USMLE) | PubMedQA | MedMCQA |
| :--- | :--- | :--- | :--- | :--- |
| **Proprietary** | **GPT-5** | **95.8%** | - | - |
| **Proprietary** | **Med-PaLM 2** | **86.5%** | **81.8%** | **72.3%** |
| **Proprietary** | **GPT-4** | 81.4%—86.1% | 75.2% | 72.4% |
| **Proprietary** | **GPT-3.5 / ChatGPT** | 60.2% | 63.9% | 57.6% |
| **Open-Source** | **MEDITRON-70B** | **70.2%** | **81.6%** | 66.0% |
| **Open-Source** | **Me-LLaMA-70B** | 62.3% | 81.4% | 64.3% |
| **Open-Source** | **Llama-2-70B** | 59.2% | 78.0% | 62.7% |
| **Open-Source** | **PMC-Llama-13B** | 45.6% | 77.8% | 54.8% |

### **Analysis of Key Concepts**
1.  **Instruction Tuning vs. Pretraining:** Research shows that while **continual pretraining** helps a model acquire deep domain knowledge (like Me-LLaMA or MEDITRON), **instruction tuning** is more cost-effective for improving immediate task performance in zero-shot settings.
2.  **Multimodal Leap:** GPT-5 represents a qualitative shift by outperforming human experts in integrating medical images with text, a task where previous models like GPT-4o struggled.
3.  **The "Safety Gap":** While open-source models like Me-LLaMA and MEDITRON offer privacy for institutional data, they are not yet recommended for real-world deployment without extensive safety alignment and clinical trials.

### Sumber:
Capabilities of GPT-5 on Multimodal Medical Reasoning - https://arxiv.org/abs/2508.08224
Towards Expert-Level Medical Question Answering with Large Language Models - https://arxiv.org/abs/2305.09617
Meditron-70B Scaling Medical Pretraining for Large Language Models - https://arxiv.org/abs/2311.16079
Medical foundation large language models for comprehensive text analysis and beyond - https://pmc.ncbi.nlm.nih.gov/articles/PMC11882967/

## VLM

### Sumber:

MMDocBench: benchmarking large vision-language models for fine-grained visual document understanding - https://arxiv.org/html/2410.21311v1
Towards Evaluating and Building Versatile Large Language Models for Medicine - https://arxiv.org/abs/2408.12547
Describe Anything Model for Visual Question Answering on Text-rich Images - https://arxiv.org/html/2507.12441v1
