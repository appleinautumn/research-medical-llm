---
title: Cost Analysis
layout: ../../components/Layout.astro
---

# Cost Analysis: API vs Self-Deployment

### **1. Proprietary API Pricing Models**
Model seperti GPT-4 atau Gemini dikembangkan oleh perusahaan swasta dan diakses melalui platform berbayar. Struktur biayanya meliputi:
*   **Usage-Based Pricing:** Most providers bill users based on the volume of data processed, commonly measured **per 1,000 or 1,000,000 tokens**. 
*   **Scalability Expenses:** While easy to implement, these models are considered **expensive at scale**, particularly for high-traffic applications or tasks requiring **long context windows**.
*   **Commercial Licensing:** In addition to usage fees, access may be governed by commercial licenses, subscription plans, or vendor-specific terms that can lead to **vendor lock-in**, making it difficult to migrate to other providers later.

### **2. Commercial API Pricing for Open-Source Models**

*   **openai/gpt-oss-120b:** $0.09 per million input tokens and **$0.45 per million output tokens**.
*   **deepseek-ai/DeepSeek-R1:** $0.50 per million input tokens and **$2.18 per million output tokens**.
*   **zai-org/GLM-4.5V:** $0.14 per million input tokens and **$0.86 per million output tokens**.

### **3. Perbandingan Faktor Biaya: API vs. Hosting Mandiri**

*   **Biaya Penggunaan API:** Model proprietary dan model proprietary yang di-host oleh pihak ketiga memiliki **recurring API fees** (biaya API berulang). model proprietary yang digunakan secara lokal **tidak memiliki biaya API berulang**, yang lebih hemat untuk penggunaan volume tinggi jangka panjang.
*   **Infrastruktur dan Pemeliharaan:** Menggunakan API menghilangkan kebutuhan akan infrastruktur lokal yang mahal. Sebaliknya, menjalankan model proprietary besar (seperti Llama 3.1 405B) memerlukan **infrastruktur yang kuat** dan perangkat keras khusus, seperti GPU 80GB, yang mungkin tidak terjangkau bagi tim kecil.
*   **Beban Manajemen:** API komersial menangani semua pembaruan, patch keamanan, dan penskalaan. Untuk model proprietary yang di-host sendiri, pengguna menanggung **beban finansial dan tenaga kerja** untuk keamanan dan pemeliharaan.

| Fitur | API Komersial/Proprietary | proprietary models (Self-Hosted) |
| :--- | :--- | :--- |
| **Biaya Utama** | **Berbasis penggunaan (per token)** | **Infrastruktur & perangkat keras** |
| **Biaya API** | Ada biaya berulang | **Tidak ada biaya API berulang** |
| **Pemeliharaan** | Dikelola oleh vendor | Dikelola pengguna (biaya tenaga kerja lebih tinggi) |
| **Skalabilitas** | Mahal pada volume tinggi | Lebih hemat untuk jangka panjang |

### Sumber:

<ul>
  <li><a href="https://jamanetwork.com/journals/jama-health-forum/fullarticle/2831206" target="_blank" rel="noopener noreferrer">Comparison of Frontier Open-Source and Proprietary Large Language Models for Complex Diagnoses</a></li>
  <li><a href="https://www.siliconflow.com/articles/en/best-open-source-LLM-for-medical-diagonisis" target="_blank" rel="noopener noreferrer">Ultimate Guide – The Best Open Source LLM for Medical Diagnosis in 2025</a></li>
  <li><a href="https://yellow.systems/blog/open-source-vs-proprietary-llms" target="_blank" rel="noopener noreferrer">Open-Source vs Proprietary LLMs: Deciding What’s Right for Your Platform</a></li>
  <li><a href="https://blog.n8n.io/open-source-llm" target="_blank" rel="noopener noreferrer">The 11 Best Open-Source LLMs for 2025</a></li>
</ul>
