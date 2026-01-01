Untuk LLM medis ada beberapa benchmark baru (MedS‑Bench, MedExQA, AMEGA, MedQA/MedMCQA/USMLE).

Untuk VLM dokumen ada MMDocBench, DocVQA, ChartQA, FlowVQA, dsb.

Dari sisi price‑to‑performance, umumnya: kalau volume token relatif kecil–menengah dan tidak butuh kontrol data ketat, **API** (Grok, GPT‑4o, Claude, dll.) lebih ekonomis; kalau trafik tinggi dan workload stabil, medical LLM on‑prem (Med42/Meditron 70B) mulai unggul di cost per token, tapi capex dan kompleksitas naik jauh.[1][2][3][4][5][6][7][8][9][10][11]

## LLM medis dan benchmark terbaru
Contoh benchmark / paper penting (open‑source & proprietary) untuk domain klinis:  

- **MedS‑Bench (2025)**: benchmark komprehensif untuk evaluasi LLM dalam konteks klinis (multi‑task, termasuk summarization dan rekomendasi).[1]
- **Med42‑v2 (Llama‑3‑based clinical LLM)**: suite model klinis (8B & 70B) dengan hasil sangat kuat di MedQA, MedMCQA, PubMedQA, USMLE, bahkan menyalip GPT‑4 base di beberapa MCQA.[12][13][14][15]
- **Llama‑3‑Meditron**: varian medical Llama‑3 (8B, 70B) yang outperform banyak open & non‑medical LLM di MedMCQA, MedQA, PubMedQA.[16][17]
- **AMEGA benchmark**: mengevaluasi 17 LLM untuk adherence ke clinical guideline di 20 case klinis kompleks (lebih ke “end‑to‑end clinical reasoning”, bukan sekadar MCQ).[4]
- **MedExQA (2024)**: medical QA benchmark berfokus pada kemampuan reasoning dan knowledge utilization, bukan cuma recall.[6]

Grok sendiri tidak punya “medical benchmark resmi”, tapi bisa dipetakan via hasil general benchmark + uji internal di MedQA/USMLE mirip cara komunitas menilai GPT‑4o/Claude untuk medis.[7][18]

### Contoh bentuk pertanyaan benchmark LLM medis
Berikut tipe & contoh gaya tanya yang umum di benchmark seperti MedQA/USMLE‑style, MedMCQA, AMEGA, MedExQA.[15][17][4][6]

1. **USMLE / MedQA‑style MCQ**  
   - “A 65‑year‑old man with a history of hypertension presents with acute onset chest pain radiating to the back. Blood pressure in the right arm is 180/100 mmHg, in the left arm 150/90 mmHg. Which of the following is the most likely diagnosis?”  
   - “A 25‑year‑old pregnant woman at 30 weeks of gestation presents with new‑onset hypertension, proteinuria, and edema. Which pathophysiologic mechanism best explains this condition?”  

2. **MedMCQA (high‑volume curriculum‑style)**  
   - “Which of the following is the most sensitive test for early diabetic nephropathy?”  
   - “First‑line therapy for Helicobacter pylori eradication in regions with low clarithromycin resistance is:”  

3. **PubMedQA / evidence‑based QA**  
   - Format: “Question (yes/no/maybe)” + short passage abstrak PubMed.  
   - Contoh: “Does early administration of oseltamivir reduce mortality in hospitalized patients with influenza pneumonia?”  

4. **Guideline adherence / AMEGA‑style**  
   Pertanyaannya berupa case panjang, lalu dievaluasi apakah rencana tatalaksana mengikuti guideline:[4]
   - “You are managing a 58‑year‑old woman with newly diagnosed stage II ER+/HER2‑ breast cancer. Describe the recommended adjuvant therapy regimen, including systemic therapy, radiotherapy, and timing according to current NCCN guidelines.”  

5. **MedExQA‑style explanation‑focused QA**  
   - “Explain why ACE inhibitors are preferred over beta‑blockers as first‑line therapy in non‑pregnant patients with diabetic nephropathy.”  
   - “For a patient with atrial fibrillation and CHA2DS2‑VASc score of 3, justify the decision to start direct oral anticoagulants instead of warfarin.”[6]

Benchmark modern cenderung menilai: akurasi jawaban, konsistensi guideline, quality of reasoning, dan ketepatan level bahasa terhadap audience (dokter vs pasien).[1][4][6]

## VLM untuk document understanding & gaya pertanyaannya
Beberapa benchmark VLM khusus dokumen/diagram:  

- **MMDocBench (2024)**: 15 task OCR‑free untuk fine‑grained document understanding (paper, receipt, laporan finansial, Wikipedia tables, charts, infografik).[10][11]
- **DocVQA**: QA di atas dokumen (form, invoice, pagescans), fokus kemampuan baca teks, layout, dan struktur.[19][20]
- **ChartQA / ChartQA‑Pro**: QA di atas grafik/diagram numerik (social/economic charts), butuh komposisi logika dan perhitungan.[8][21]
- **FlowVQA**: QA di atas flowchart, fokus reasoning topologis & alur proses.[22]

### Contoh bentuk pertanyaan VLM dokumen
Berikut gaya tanya dari DocVQA, ChartQA, FlowVQA, dan MMDocBench.[8][10][19][22]

1. **DocVQA / Invoice / Form**  
   - “What is the invoice number?” (dokumen: invoice PDF)  
   - “What is the due date of this invoice?”  
   - “Who is the billing address recipient?”  
   - “What is the total amount including tax?”  

2. **Long document (paper, report) – MMDocBench**  
   - “What is the title of the paper?”  
   - “According to the abstract, what is the main contribution of the method?”  
   - “In Table 2, what is the accuracy of Model B on the CIFAR‑10 dataset?”  

3. **ChartQA / ChartQA‑Pro (grafik)**  
   - “What was the unemployment rate in 2015?”  
   - “By how many percentage points did the GDP growth in 2020 differ from 2018?”  
   - “Which country had the highest CO₂ emissions in 2019?”[21][8]

4. **FlowVQA (flowchart)**  
   - “What is the first step after the user logs in?”  
   - “According to the flowchart, under what condition does the system send an error message?”  
   - “How many decision nodes appear before the ‘End’ node?”[22]

5. **Complex document reasoning (MMDocBench)**  
   - “According to the financial report, what is the net profit for Q2 2023?”  
   - “In the bar chart, which product category has the lowest sales in Europe?”[11][10]

## Price‑to‑performance: API vs on‑prem (LLM medis)
Berikut ringkasan indikatif (harga per 1M input / output token, USD, late‑2024–2025; selalu cek pricing resmi saat implementasi):[9][18][23][24][25][26][7]

| Model / Layanan                       | Tipe     | Price (input/output per 1M tok) | Keterangan singkat                                                                 |
|--------------------------------------|----------|----------------------------------|------------------------------------------------------------------------------------|
| **Grok 4.1 Fast**                    | API      | ~0.20 / 0.50 [7]           | Model reasoning cepat, 2M context, sangat murah untuk kelasnya.                   |
| **Grok 3**                           | API      | 3.00 / 15.00 [27][28]   | Model besar general‑purpose, mirip kelas GPT‑4o/Claude Sonnet.                    |
| **GPT‑4o**                           | API      | 2.50 / 10.00 [26]           | Strong general + bagus untuk medis, vision, tool use.                             |
| **GPT‑4o mini**                      | API      | 0.15 / 0.60 [24][9][26] | Model kecil super murah, cukup kuat untuk QA medis menengah.                  |
| **Claude 3.5 Sonnet**                | API      | 3.00 / 15.00 [23][26]   | Reasoning kuat, bagus untuk teks panjang & klinis kompleks.                       |
| **Claude Haiku 4.5 / 3.5 Haiku**     | API      | ~1.00 / 5.00 klas 2025 [25] | Model kecil cepat, cost rendah.                                                   |
| **Med42‑v2 70B (hosted / API)**      | API/host | ~setara GPT‑4o tier (est.) [12][14] | Biasanya priced premium kalau pakai hosted provider.                        |
| **On‑prem 70B (Med42/Meditron)**     | On‑prem  | CAPEX GPU (mis. 2× H100 80GB) [2][3][5] | Cost per token turun tajam jika util tinggi. |
| **On‑prem 8B (Med42‑8B)**            | On‑prem  | GPU kelas L40S/RTX A6000 [2][5] | Murah, tapi performa medis di bawah 70B.                                          |

Secara performa medis (MedQA, MedMCQA, USMLE, dll.), berbagai laporan menyebut:[13][14][17][12][15][16]

- Med42‑v2‑70B dan Llama‑3‑Meditron‑70B ≈ atau > GPT‑4‑class di banyak MCQA medis.  
- Grok 4‑class & GPT‑4o & Claude Sonnet berada di range akurasi tinggi (sekitar 80–90% di USMLE‑style, tergantung konfigurasi & prompting).[18][13]
- Model kecil (GPT‑4o mini, Med42‑8B, dll.) di range menengah (70–80%) tetapi cost per token jauh lebih rendah.[24][26][12][16]

### Scatter plot price vs performance (indikatif)
Berikut scatter plot **price‑to‑performance** (X = indeks harga relatif per 1M token, Y = skor performa relatif di medical QA; semakin kanan‑atas semakin mahal & bagus):
- Contoh titik:  
  - Grok 4.1 Fast API: (harga ~0.1, skor ~82).  
  - GPT‑4o API: (1.0, 85).  
  - Claude 3.5 Sonnet API: (1.1, 87).  
  - GPT‑4o mini API: (0.06, 75).  
  - Grok 3 API: (1.0, 80).  
  - Med42‑70B API: (1.0, 90).  
  - Med42‑70B on‑prem: (0.3, 90).  
  - Meditron‑70B on‑prem: (0.28, 83).  
  - Med42‑8B on‑prem: (0.08, 78).  

Interpretasi praktis (rule of thumb):  

- **Sweet spot “murah tapi cukup pintar”**: GPT‑4o mini, Grok 4.1 Fast, Med42‑8B on‑prem untuk use case: triage, FAQ klinis sederhana, coding medis ringan.[26][7][24]
- **High‑stakes / konsultasi klinis kompleks**: Med42‑70B (API atau on‑prem), Llama‑3‑Meditron‑70B, GPT‑4o / Claude Sonnet jika butuh reasoning panjang + tool integration.[17][12][13][16]
- **On‑prem 70B** mulai menang **cost per token** bila:  
  - Volume stabil di ratusan juta – miliaran token per bulan.  
  - Server H100/L40S terutilisasi tinggi (bukan idle).  
  - Ada alasan kuat (compliance, data residency, latency lokal).[2][3][5]

## Kapan pilih API vs deploy sendiri (LLM & VLM)
### API cocok jika…
- Volume token masih **fluktuatif / kecil‑menengah** (mis. <100–200 juta token/bulan), jadi beli GPU sendiri belum ekonomis.[5][9]
- Tidak ada hard requirement on‑prem (HIPAA‑level data bisa tetap via BAA/cloud private endpoint).[3]
- Butuh model **state‑of‑the‑art** terus update (Grok 4.x, GPT‑4o, Claude 3.5) tanpa maintain infra & fine‑tuning.[23][7][18][26]
- Waktu go‑live penting: integrasi API jauh lebih cepat.  

### On‑prem cocok jika…
- Use case rumah sakit / jaringan klinik besar dengan **volume tinggi & stabil** (RAG EHR, auto‑coding, summarization semua visit, dsb.).[3][5]
- Ada persyaratan **regulator / data sovereignty** untuk menyimpan data di DC sendiri atau di Indonesia.[3]
- Ada tim infra/ML Ops dan budget CAPEX GPU (H100/L40S) + engineer untuk maintain stack (vLLM/TGI, monitoring, autoscaling).[2][5]

Rule cepat:  
- Kalau belum yakin tembus > ~200–300 juta token/bulan selama 12–24 bulan, **API** hampir selalu win secara TCO.[5][9][26]
- Di atas itu, cluster 2×H100 atau beberapa L40S dengan model 70B yang well‑optimized bisa turunkan effective cost per 1M token menjadi fraksi dari harga Grok/GPT‑4o/Claude, dengan syarat utilisasi tinggi.[2][5][3]

## Contoh spec on‑prem & kapasitas (kasar)
Ini gambaran konfigurasi yang realistis untuk use case medis di enterprise; angka QPS sangat tergantung context length, sampling, dan quantization.[29][30][5][2][3]

### 1) Cluster 70B (Med42 / Llama‑3‑Meditron 70B)
- **Hardware tipikal**  
  - 1 server 2× NVIDIA H100 80GB (atau 4× L40S 48GB).  
  - CPU 32–64 core, RAM 256–512 GB, NVMe SSD 4–8 TB.[5][2][3]
- **Model**  
  - Med42‑v2‑70B, Llama‑3‑Meditron‑70B, running via vLLM/TGI 4‑bit/8‑bit.[12][16][17]
- **Target user / throughput** (orde magnitudo, context 2–4k, jawaban 512 token, batching):  
  - ±20–50 req/s untuk teks murni dengan batching agresif.  
  - Cukup untuk **ratusan–seribu** user concurrency ringan (mis. dokter yang kadang query).[5]
- **Profil**  
  - Cocok untuk: guideline QA, supporting decision, auto‑summary visit, coding medis, dsb.  
  - Perlu MLOps: observability, autoscaling (jika multi‑node), model updates.  

### 2) Node 8B (Med42‑8B) untuk workload medium
- **Hardware tipikal**  
  - 1 server 2× L40S 48GB (atau 1× A6000 48GB untuk beban sedang).[29][2][5]
  - CPU 16–32 core, RAM 128–256 GB, SSD 2–4 TB.  
- **Model**  
  - Med42‑8B / Llama‑3‑Meditron‑8B 4‑bit.[16][17][12]
- **Target user**  
  - Puluhan QPS teks, cukup untuk **ratusan** user internal.  
  - Cocok jadi **tier‑1 triage model** + RAG, eskalasi ke API GPT‑4o / Grok / Med42‑70B hanya untuk kasus sulit.  

### 3) VLM Document Understanding (MMDocBench / DocVQA‑like)
Untuk VLM open‑source (mis. Qwen‑VL, InternVL, LLava‑type) yang dipakai parse: invoice, rekam medis PDF, laporan lab, dsb.:[31][32][10][19]

- **Hardware tipikal**  
  - 1× L40S 48GB / A6000 48GB untuk model 7–34B vision‑language.[32][5]
  - CPU 16–32 core, RAM 128–256 GB.  
- **Kapasitas**  
  - Beberapa QPS untuk dokumen berat (karena ada langkah vision encoding); cocok buat batch processing (ETL dokumen) atau API internal yang tidak super‑latency critical.[33][31][32]

Kalau ingin, langkah berikut bisa dibuat sangat konkret:  
- Pilih 2–3 task medis prioritas (mis. USMLE‑style QA, guideline adherence, discharge summary).  
- Pilih 3–4 kandidat model (Grok 4.1 Fast, GPT‑4o mini, GPT‑4o, Med42‑8B on‑prem).  
- Desain mini‑benchmark internal: 50–100 case mirip contoh di atas (LLM + VLM) dan logging cost/token untuk hitung **score per dolar**.

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