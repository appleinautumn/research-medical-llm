---
title: VLM Benchmarks
---

# VLM Benchmarks for Document Understanding

### **1. Fine-Grained Perception: MMDocBench**
**MMDocBench** is a comprehensive benchmark designed to assess the **fine-grained visual perception** and reasoning abilities of VLMs in an OCR-free manner. 
*   **Composition:** It defines **15 main tasks** with **4,338 QA pairs** and over 11,000 supporting regions.
*   **Document Diversity:** It covers a wide array of document types, including **research papers, receipts, financial reports, Wikipedia tables, charts, and infographics**.
*   **Significance:** Unlike object-level assessments in natural images, this benchmark uses multi-granularity information to evaluate how well models can reason over intricate document structures.

### **2. Advanced Multimodal Reasoning: MMMU-Pro and MMT-Bench**
As standard benchmarks like MMMU reached their limits, more rigorous versions were introduced to measure "true understanding".
*   **MMMU-Pro:** This is an advanced version of the original MMMU. It introduces a **vision-only input setting** and increases the number of answer options from four to ten. It also simulates real-world conditions by using screenshots with varying backgrounds and font styles.
*   **MTT-Bench:** This large-scale benchmark includes over **31,000 multi-choice questions** across 162 subtasks. It specifically evaluates capabilities in **OCR, visual recognition, and visual-language retrieval** across image, text, and video modalities.

### **3. Specialized Document Tasks: ViDoRe and FUNSD**
The sources highlight benchmarks that focus on specific document processing workflows:
*   **ViDoRe (Visual Document Retrieval):** This benchmark is the standard for **multimodal retrieval** tasks. It evaluates how well models can find the most relevant page in a stack of PDFs (such as financial reports or scientific documents) based on a query. It features documents in both **English and French**.
*   **FUNSD:** A well-known benchmark for **form understanding in noisy, scanned documents**. While valuable for its focus on heterogeneous elements like checkboxes and signatures, it is limited in scale, containing only **199 forms**.

### **4. Performance Trends in Document Understanding**
*   **Frontier Performance:** Models like **GLM-4.5V** have demonstrated state-of-the-art results on 41 multimodal benchmarks, particularly excelling in analyzing clinical charts and complex spatial relationships using technologies like 3D-RoPE.
*   **Reasoning Models:** Newer "thinking" models, such as **Skywork R1V2**, have achieved high scores on technically demanding benchmarks, including 73.6 on MMMU and 62.6 on **OlympiadBench**.
*   **VLM vs. Traditional OCR:** In form-centric tasks, VLMs consistently outperform traditional systems like Tesseract and PP-OCR because they can jointly reason over visual regions and textual content rather than processing isolated text blocks.

### Sumber

<ul>
  <li><a href="https://huggingface.co/blog/vlms-2025" target="_blank" rel="noopener noreferrer">Hugging Face Blog: Vision Language Models in 2025</a></li>
  <li><a href="https://arxiv.org/abs/2410.21311" target="_blank" rel="noopener noreferrer">arXiv Paper: MMDocBench</a></li>
  <li><a href="https://openreview.net/forum?id=WK6hQoAtgx" target="_blank" rel="noopener noreferrer">OpenReview: MMDocBench Submission</a></li>
  <li><a href="https://bnaic2025.unamur.be/accepted-submissions/accepted_oral/037%20-%20Synthetic%20Document%20Generation%20for%20Form%20Understanding%20with%20Vision-Language%20Models.pdf" target="_blank" rel="noopener noreferrer">BNAIC 2025: Synthetic Document Generation for Form Understanding</a></li>
</ul>
