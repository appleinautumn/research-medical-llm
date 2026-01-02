
<style>
  .image-container {
    max-width: 100%;
    overflow: hidden;
  }

  .image-container img {
    width: 100%;
    height: auto;
  }
</style>

- [Benchmark LLM](#llm)
- [Benchmark VLM](#vlm)
- [Pricing](#pricing)

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
- Capabilities of GPT-5 on Multimodal Medical Reasoning - https://arxiv.org/abs/2508.08224
- Towards Expert-Level Medical Question Answering with Large Language Models - https://arxiv.org/abs/2305.09617
- Meditron-70B Scaling Medical Pretraining for Large Language Models - https://arxiv.org/abs/2311.16079
- Medical foundation large language models for comprehensive text analysis and beyond - https://pmc.ncbi.nlm.nih.gov/articles/PMC11882967/

## VLM

The sources identify **GPT-5** as the new state-of-the-art (SOTA) leader in multimodal reasoning, particularly in complex domains, while **GPT-4o** and **Qwen-VL-Max** remain top performers for general document understanding and spatial grounding.

### **Best Proprietary VLMs**
Proprietary models lead the field in holistic reasoning and high-stakes diagnostic accuracy.

*   **GPT-5:** Described as a "generalist multimodal reasoner," it achieves **super-human proficiency** in complex multimodal evaluations. It provides a "dramatic leap" over GPT-4o, improving multimodal reasoning and understanding scores by **+29.26% and +26.18%** respectively on the MedXpertQA MM benchmark. It is significantly more capable of synthesizing visual and textual cues to arrive at accurate clinical decisions.
*   **GPT-4o:** Remains a top-tier model for **answer prediction accuracy** in general document reasoning, scoring highest on the MMDocBench (66.40% Exact Match).
*   **Qwen-VL-Max:** The leading proprietary model for **visual grounding (region prediction)**, achieving the highest IOU score (11.44%) on MMDocBench. It is particularly strong in region prediction across general, table-based, and chart-based documents.
*   **Gemini-2.5-Flash:** Cited as a high-performing generalist that sets a "high performance bar" on text-rich benchmarks like InfographicVQA and ChartQA.

### **Best Open-Source VLMs**
Open-source models have become highly competitive, often surpassing proprietary models in specialized spatial tasks or specific reasoning categories.

*   **Llava-OV-Chat-72B:** The highest-performing open-source model for **answer prediction**, scoring 58.93% on MMDocBench. It uniquely outperforms all other models—proprietary or open—in **Logical Reasoning** and **Spatial Reasoning**.
*   **Qwen2.5-VL:** A state-of-the-art generalist model that rivals proprietary suites in text-rich VQA and holistic image understanding.
*   **TextMonkey:** The premier open-source model for **fine-grained visual perception**, specifically region prediction (19.22% IOU). It is the best model overall for interpreting **infographic-based documents**.
*   **InternVL2-Llama3-76B:** Recognized as a leading open-source suite that closes the performance gap with commercial multimodal models.
*   **DAM-QA:** The best-performing **region-aware model** among its peers (e.g., Shikra, Ferret), demonstrating significant gains in document-centric tasks (DocVQA) through its sliding-window architecture.

### **Best Domain-Specific VLMs**
*   **Medical/Clinical:** **MMedIns-Llama 3** is a specialized open-source model that significantly outperforms GPT-4 and Claude-3.5 across a wide array of clinical tasks, including diagnosis, treatment planning, and information extraction. 

***

To visualize the hierarchy, you can think of **GPT-5** as a **senior consultant** who has reached a level of insight that exceeds even trained human experts in complex cases, while **Qwen-VL-Max** and **TextMonkey** are like **high-precision microscopes** that are best at physically locating the smallest details on a slide.

### Sumber:

- MMDocBench: benchmarking large vision-language models for fine-grained visual document understanding - https://arxiv.org/html/2410.21311v1
- Towards Evaluating and Building Versatile Large Language Models for Medicine - https://arxiv.org/abs/2408.12547
- Describe Anything Model for Visual Question Answering on Text-rich Images - https://arxiv.org/html/2507.12441v1

## Pricing

### a. Harga API (indikatif 2025)
Ringkasan kasar untuk 1M token (cek lagi portal resmi saat implementasi):

| Model / Layanan          | Tipe | Est. harga input / output per 1M token | Catatan                                                                 |
|--------------------------|------|----------------------------------------|-------------------------------------------------------------------------|
| Grok 4.1 Fast            | API  | ~$0.20 / ~$0.50                        | Sangat murah untuk kelasnya, 2M context, cocok beban tinggi. [12]  |
| Grok 3                   | API  | ~\$3 / \$15                            | Kelas GPT‑4o/Claude Sonnet. [10][11]                            |
| GPT‑4o                   | API  | ~\$2.5 / \$10                          | General + medis kuat, multimodal. [8][37][38]             |
| GPT‑4o mini              | API  | ~\$0.15 / \$0.60                       | Sangat murah, cukup untuk QA medis menengah. [34][36][8]  |
| Claude 3.5 Sonnet        | API  | ~\$3 / \$15                            | Reasoning panjang & teks kompleks. [9][8]                    |
| Claude Haiku (3.x/4.5)   | API  | ~\$1 / \$5                             | Model kecil cepat. [35]                                            |
| Med42‑70B (hosted/API)   | API  | kisaran premium setara GPT‑4o          | Tergantung provider. [2][3][4]                             |
| GPT‑5                    | API  | ~\$1.25 / \$10                         | Input lebih murah dari GPT‑4o, performa jauh lebih tinggi. [39][40][41][42] |
| gpt‑5‑mini               | API  | ~\$0.25 / \$2                          | Versi kecil, bagus untuk workload ringan. [39][40]             |

Kalau dinormalisasi dengan **indeks harga** (GPT‑4o = 1.0) dan **indeks performa medis** (MedQA/USMLE‑style):

- GPT‑4o: price index ~1.0, performa medis ~85.[15][8]
- Claude 3.5 Sonnet: p ~1.1, perf ~87.[9][8]
- Grok 3: p ~1.0, perf ~80.[10][11][12]
- Grok 4.1 Fast: p ~0.1, perf ~82.[12]
- GPT‑4o mini: p ~0.06, perf ~75.[34][36][8]
- Med42‑70B API: p ~1.0, perf ~90.[2][3][4][5]
- **GPT‑5**: p ~0.5–0.6, perf ~95–96.[13][14][17][39][15]

Secara price‑to‑performance murni, GPT‑5 adalah titik yang sangat dominan: lebih murah per input token dari GPT‑4o tapi jauh lebih akurat, termasuk di benchmark medis yang AIMultiple pakai (MedQA).[1][14][39][13][15]

#### Sumber:
[1](https://www.nature.com/articles/s41746-024-01390-4)
[2](https://gist.github.com/Teebor-Choka/a4a5b099b85404538e32eb8a06c71565)
[3](https://kairntech.com/blog/articles/llm-on-premise/)
[4](https://pmc.ncbi.nlm.nih.gov/articles/PMC11638254/)
[5](https://basebox.ai/blog/local-ai-enterprise-scale-practical-insights-and-tooling-for-on-premise-llms)
[6](https://aclanthology.org/2024.bionlp-1.14.pdf)
[7](https://costgoat.com/pricing/grok-api)
[8](https://arxiv.org/html/2507.12441v1)
[9](https://www.vantage.sh/blog/gpt-4o-small-vs-gemini-1-5-flash-vs-claude-3-haiku-cost)
[10](https://arxiv.org/abs/2410.21311)
[11](https://mmdocbench.github.io)
[12](https://huggingface.co/m42-health/Llama3-Med42-8B)
[13](https://www.emergentmind.com/topics/med42-llama3-1-70b)
[14](https://arxiv.org/html/2408.06142v1)
[15](https://openreview.net/pdf?id=oulcuR8Aub)
[16](https://openreview.net/pdf?id=ZcD35zKujO)
[17](https://ai.meta.com/blog/llama-2-3-meditron-yale-medicine-epfl-open-source-llm/)
[18](https://intuitionlabs.ai/articles/ai-api-pricing-comparison-grok-gemini-openai-claude)
[19](https://evalscope.readthedocs.io/en/latest/get_started/supported_dataset/vlm.html)
[20](https://www.scribd.com/document/662752205/DOCVQA1)
[21](https://openaccess.thecvf.com/content/ICCV2025W/VisionDocs/papers/Vu_Describe_Anything_Model_for_Visual_Question_Answering_on_Text-rich_Images_ICCVW_2025_paper.pdf)
[22](https://aclanthology.org/2024.findings-acl.78.pdf)
[23](https://pieces.app/blog/how-to-use-gpt-4o-gemini-1-5-pro-and-claude-3-5-sonnet-free)
[24](https://docsbot.ai/models/compare/gpt-4o-mini/claude-3-5-haiku)
[25](https://skywork.ai/blog/claude-haiku-4-5-vs-gpt4o-mini-vs-gemini-flash-vs-mistral-small-vs-llama-comparison/)
[26](https://blog.promptlayer.com/big-differences-claude-3-5-vs-gpt-4o/)
[27](https://www.linkedin.com/pulse/xai-launches-grok-3-api-four-pricing-tiers-intensifying-%E6%9D%B0-%E9%82%93-q1qic)
[28](https://apidog.com/blog/grok-4-pricing/)
[29](https://www.reddit.com/r/LocalLLaMA/comments/1iglg8t/need_advice_on_hardware_for_running_a_70b_local/)
[30](https://www.reddit.com/r/LocalLLaMA/comments/1eiwnqe/hardware_requirements_to_run_llama_3_70b_on_a/)
[31](https://www.ijcrt.org/papers/IJCRT2512402.pdf)
[32](https://nanonets.com/blog/vision-language-model-vlm-for-data-extraction/)
[33](https://arxiv.org/html/2510.15727v2)
[34](https://arxiv.org/html/2404.14779v1)
[35](https://the-rogue-marketing.github.io/grok-api-latest-llms-pricing-october-2025/)
[36](https://www.businesswaretech.com/blog/research-ai-models-invoice-processing-benchmark)
[37](https://github.com/SCUT-DLVCLab/Document-AI-Recommendations/blob/main/Approaches/approaches_vie.md)
[38](https://unstructured.io/blog/benchmarking-document-parsing-and-what-actually-matters)
[39](https://www.johnsnowlabs.com/visual-document-understanding-benchmark-comparative-analysis-of-in-house-and-cloud-based-form-extraction-models/)
[40](https://raw.githubusercontent.com/mlresearch/v260/main/assets/he25a/he25a.pdf)

### b. Scatter plot (gambaran visual price vs performance)

<div class="image-container">

![plot](/images/plot.png)

</div>

## Ringkasan plot (X = indeks harga lebih murah ke kiri, Y = skor MedQA lebih tinggi ke atas)
- **Dominan points** (sweet spot kanan atas tapi tidak terlalu mahal):  
  - **GPT‑5 API** (~0.55 harga, 96 skor) → Paling unggul P2P, sedikit lebih mahal dari GPT‑4o tapi akurasi jauh lebih tinggi.[1][2][3][4]
  - **GPT‑5 VLM** (~0.65 harga, 95 skor) → Untuk multimodal (dokumen + gambar); cost sedikit naik karena vision input.[2][5][6]
  - **Med42‑70B API/on‑prem** (1.0/0.3 harga, 90 skor) → Open medical LLM kuat; on‑prem menang kalau volume tinggi.[7][8][9][10][11]

- **Cost leaders** (kiri bawah, murah tapi cukup pintar):  
  - **GPT‑4o mini** (0.06, 75)  
  - **Grok 4.1 Fast** (0.1, 82)  
  - **Med42‑8B on‑prem** (0.08, 78) → Bagus untuk triage lokal.[10][12][13][14]

- **Premium/high perf tapi mahal** (kanan atas):  
  - **Med‑PaLM 2** (1.2, 87) → Kuat clinical QA tapi harga enterprise.[15][16][17]
  - **Claude 3.5 Sonnet** (1.1, 87)  

- **Base model** (tidak direkomendasikan tanpa tuning):  
  - **Llama 3 70B base on‑prem** (0.25, 65) → Fondasi Med42/Meditron, tapi QA medis lemah tanpa fine‑tuning.[18][19][20]

## Insight
- **Untuk volume rendah–menengah**: **GPT‑5 API/VLM** jadi pilihan utama (terbaik P2P absolut).[1][2][3][4]
- **Untuk volume tinggi + data residency**: **Med42‑70B on‑prem** atau **Med42‑8B** untuk triage → eskalasi ke GPT‑5 API hanya kasus sulit.[7][8][9][10][11]
- **Hybrid ideal**: Gunakan plot ini untuk “tiering” – murah untuk 80% workload sederhana, premium untuk 20% kompleks.

#### Sumber:
[1](https://www.cursor-ide.com/blog/gpt-5-api)
[2](https://arxiv.org/abs/2508.08224)
[3](https://binaryverseai.com/gpt-5-medical-2025-studies-multimodal-mri/)
[4](https://www.ainews.com/p/gpt-5-surpasses-doctors-in-medical-reasoning-benchmarks)
[5](https://arxiv.org/html/2410.21311v1)
[6](https://openreview.net/forum?id=WK6hQoAtgx)
[7](https://huggingface.co/m42-health/Llama3-Med42-8B)
[8](https://www.emergentmind.com/topics/med42-llama3-1-70b)
[9](https://arxiv.org/html/2408.06142v1)
[10](https://huggingface.co/m42-health/Llama3-Med42-70B)
[11](https://skywork.ai/blog/models/llama3-med42-70b-free-chat-online-skywork-ai/)
[12](https://costgoat.com/pricing/grok-api)
[13](https://docsbot.ai/models/compare/gpt-4o-mini/claude-3-5-haiku)
[14](https://www.vantage.sh/blog/gpt-4o-small-vs-gemini-1-5-flash-vs-claude-3-haiku-cost)
[15](https://arxiv.org/pdf/2305.09617.pdf)
[16](https://dr7.ai/blog/model/top-5-medical-ai-models-compared-medgemma-gpt-4-med-palm-2-more/)
[17](https://pmc.ncbi.nlm.nih.gov/articles/PMC11922739/)
[18](https://openreview.net/pdf?id=ZcD35zKujO)
[19](https://ai.meta.com/blog/llama-2-3-meditron-yale-medicine-epfl-open-source-llm/)
[20](https://arxiv.org/pdf/2311.16079.pdf)
