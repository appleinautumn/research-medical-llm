---
title: LLM Benchmarks
layout: ../../components/Layout.astro
---

## 1. Benchmark LLM medis

### **1. Medical and Clinical Benchmarks**
The evaluation of LLMs in healthcare has moved beyond simple multiple-choice exams to simulate real-world clinical complexity.
*   **ClinBench:** Unlike traditional benchmarks derived from exam questions, ClinBench uses **authentic clinical cases from authoritative medical journals**, providing over 2,000 questions that simulate actual practice.
*   **USMLE & MedQA:** The United States Medical Licensing Examination (USMLE) remains a standard for clinical reasoning. Recent evaluations on MedQA datasets show that **reasoning models (like OpenAI o1 and GPT-5 Mini)** lead in accuracy, followed closely by models like Claude Opus 4.1 and Grok 4.
*   **Open Medical-LLM Leaderboard:** This platform aggregates diverse datasets, including **MedMCQA** (Indian medical entrance exams), **PubMedQA** (scientific literature comprehension), and medical subsets of **MMLU** such as Clinical Knowledge and Anatomy.
*   **Bias Detection:** A critical component of modern medical benchmarking is the injection of **deliberate racial bias** to test robustness. Results indicate that models like o1, Llama 3.1, and Gemini 1.5 Pro show statistically significant performance variations across different races, revealing potential **racial bias** in their training data.

### **2. General Reasoning and Technical Benchmarks**
For general intelligence and specialized technical skills, the industry relies on a suite of "frontier" benchmarks:
*   **Reasoning & Math:** **DeepSeek-R1** and **OpenAI o1** currently set the bar for advanced reasoning, excelling in benchmarks like **MATH**, **GSM8K**, and the **AIME 2025**.
*   **Coding:** Models are evaluated on their ability to generate and verify code using **HumanEval**, **LiveCodeBench**, and **SWE-Bench Verified**.
*   **Knowledge & Logic:** **MMLU-Pro** and **GPQA** (Graduate-Level Google-Proof Q&A) are used to assess higher-level academic and scientific reasoning that goes beyond simple factual recall.

### **3. Multimodal and Document Understanding (LVLM)**
Vision-Language Models (VLMs) require benchmarks that test the integration of visual and textual data.
*   **Fine-Grained Perception:** **MMDocBench** holistically assesses capabilities through 15 tasks covering research papers, financial reports, and infographics.
*   **High-Complexity Vision:** **MMMU-Pro** and **MMT-Bench** address benchmark saturation by introducing vision-only inputs and increasing answer options (up to 10) to minimize "lucky guesses".
*   **Visual Retrieval:** **ViDoRe** (Visual Document Retrieval) is the primary benchmark for assessing a model's ability to retrieve specific information from complex document stacks, such as finding the correct page in a financial report.

### **4. Comparative Performance: Open-Source vs. Proprietary**
Recent benchmarking reveals a closing gap between proprietary and open-source models:
*   **Differential Diagnosis:** In complex medical cases, the open-source **Llama 3.1 405B** has demonstrated performance **on par with GPT-4**, correctly identifying final diagnoses in 70% of challenging cases.
*   **Specialized Medical Models:** Models such as **DeepSeek-R1** and **GLM-4.5V** provide competitive alternatives to proprietary systems for complex differential diagnosis and medical imaging analysis.

| Category | Key Benchmarks | Top Performing / Notable Models |
| :--- | :--- | :--- |
| **Medical** | ClinBench, MedQA, USMLE | o1, GPT-5 Mini, DeepSeek-R1, Llama 3.1 |
| **Reasoning** | MATH, GPQA, AIME | DeepSeek-R1, OpenAI o1 |
| **Vision** | MMMU-Pro, MMDocBench | GLM-4.5V, Qwen2.5-VL |
| **Coding** | HumanEval, SWE-Bench | GPT-4o, DeepSeek-V3 |

### Sumber:

<ul>
  <li><a href="https://huggingface.co/blog/leaderboard-medicalllm" target="_blank">Hugging Face: Open Medical-LLM Leaderboard</a></li>
  <li><a href="https://openreview.net/forum?id=R1u1qWfosc" target="_blank">OpenReview: MMDocBench Submission (R1u1qWfosc)</a></li>
  <li><a href="https://jamanetwork.com/journals/jama-health-forum/fullarticle/2831206" target="_blank">JAMA Health Forum: Open-Source vs. Closed-Source LLMs in Diagnostic Reasoning</a></li>
  <li><a href="https://sciety.org/articles/activity/10.21203/rs.3.rs-6651111/v1" target="_blank">Sciety: Benchmarking LLMs on USMLE (Preprint)</a></li>
  <li><a href="https://llm-stats.com/benchmarks" target="_blank">LLM Stats: Benchmarks Overview</a></li>
  <li><a href="https://www.vals.ai/benchmarks/medqa-03-28-2025" target="_blank">VALS.ai: MedQA Bias Evaluation (March 28, 2025)</a></li>
  <li><a href="https://www.nature.com/articles/s41415-025-8383-2" target="_blank">Nature: Racial Bias in Medical LLMs (s41415-025-8383-2)</a></li>
  <li><a href="https://www.vals.ai/benchmarks/medqa" target="_blank">VALS.ai: MedQA Benchmark Overview</a></li>
</ul>
