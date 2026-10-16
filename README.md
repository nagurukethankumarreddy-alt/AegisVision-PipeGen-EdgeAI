# 🛡️ AegisVision: Real-Time Industrial Safety, Fall Posture & Privacy-Preserving Edge Sentinel
**Event:** HackWithBangalore 4.0 — CraftifAI PipeGen Track A (v0.5.1)  
**Team:** sync4ce  
**Bonus Targeted:** Edge Optimization Bonus (TensorRT INT8 Quantization & DeepStream Benchmarking)

---

## 👥 Meet Team sync4ce

* **Naguru Kethan (Team Lead & Full-Stack AI Builder)**
  * **Bio:** Full-Stack AI & Computer Vision Builder @ PES University | Data Analyst @ Nexus AWS Club | 2nd Runner-Up @ SustainX Hackathon. Shipped 6+ end-to-end production systems spanning Microsoft Azure AI (Speech/Translator), Contactless rPPG Biosensing (OpenCV/PCA), Enterprise Agentic AI, and Geospatial Civic Platforms.
  * **Tech Stack:** Python, Microsoft Azure, AWS, OpenCV, Agentic AI, FastAPI, React, JavaScript, Streamlit, C, Folium, Computer Vision, Machine Learning, Cloudflare, Git, Linux.

* **Joshika Kuntimaddi (Frontend & Computer Vision Lead)**
  * **Bio:** Frontend, Geospatial UI & Computer Vision Developer @ PES University. Experienced in building interactive Smart City heatmaps, multimodal vision dashboards, and responsive web applications using Streamlit, Folium, React, and OpenCV.
  * **Tech Stack:** Python, React, JavaScript, HTML, CSS, Streamlit, Folium, OpenCV, Figma, UI/UX, TailwindCSS, Git.

* **Namita Sherakhane (AI & Backend Systems Lead)**
  * **Bio:** AI & Backend Systems Developer specializing in Agentic AI workflows, LLM document parsing, and scalable REST APIs. Experienced in building automated compliance auditors, edge health APIs, and cloud-native backends.
  * **Tech Stack:** Python, FastAPI, Node.js, Agentic AI, LangChain, Microsoft Azure, AWS, SQL, REST APIs, NLP, Git, Linux.

* **Manya Agarwal (Data Analytics & Cloud FinOps Lead)**
  * **Bio:** Data Analytics, Cloud FinOps & AI Product Builder. Focused on statistical modeling, time-series anomaly detection, SaaS license optimization engines, and data-driven product strategy.
  * **Tech Stack:** Python, Data Analytics, Machine Learning, Pandas, NumPy, SQL, AWS, Microsoft Azure, Streamlit, FinOps, Git.

---

## 1. Problem Statement
Industrial manufacturing floors and high-risk work zones suffer from preventable injuries because traditional CCTV systems only provide passive post-incident recordings. When a worker enters a hazardous machinery zone or suffers a sudden fall, every millisecond counts—yet streaming raw high-definition video to the cloud introduces unacceptable network latency and violates worker privacy.

## 2. Our Solution (Built in CraftifAI PipeGen v0.5.1)
**AegisVision** is an ultra-low-latency Physical AI perception-to-action pipeline built end-to-end across all five stages of **CraftifAI PipeGen** (`Requirement → Pipeline IR → Model → Compiler → Run`):
- **Inputs:** Live USB Camera and industrial floor video streams under `/home`.
- **Tasks & Pipeline IR:** Multi-stage DeepStream graph performing primary person detection, pose keypoint estimation, multi-object tracking (persistent worker IDs), Polygon ROI Hazard Zone checking, and temporal fall-posture verification.
- **Models & Precision (Edge Optimization Bonus):** Compiled ONNX vision models into **TensorRT INT8** and **FP16** engines using PipeGen's Compiler stage.
- **Actionable Outputs (Beyond Bounding Boxes):** Publishes real-time structured JSON incident payloads and low-latency **MQTT safety triggers** (`Topic: aegis/safety/alerts`) consumed by our live **AegisVision OSHA Incident Command Center**.

## 3. Edge Optimization Bonus: Speed, Power & Accuracy Trade-Off Report
Using PipeGen's TensorRT profiler:
- **INT8 Quantization Advantage:** Compiling to INT8 reduced per-frame inference latency by **~69%** and cut GPU power draw while maintaining **>93.5% mAP accuracy** (less than 0.6% accuracy trade-off compared to FP32), proving it runs efficiently on edge Jetson units.

## 4. Verification Evidence & Prototype Structure
- `pipegen_export/`: Generated DeepStream application, configs, and `run.sh` from PipeGen.
- `aegis_dashboard.py`: Fully functional Streamlit interactive prototype dashboard simulating real-time MQTT event ingestion, hazard lockout triggering, and TensorRT edge optimization performance metrics.
- `evidence/`: Contains Pipeline IR graph and TensorRT INT8 speed benchmark reports.
