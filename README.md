# 🚁 UAV Traffic Scene Understanding: A Cross-Spectral Guided Approach and a Unified Benchmark

[![Hugging Face Datasets](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Datasets-blue)](https://huggingface.co/datasets/YuYu2004/Traffic-VQA)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE)


> **TL;DR:** We introduce Traffic-VQA, the first large-scale optical-thermal infrared (OPT-TIR) benchmark for UAV traffic understanding, and propose CTCNet, a novel Cross-spectral Traffic Cognition Network for robust all-weather traffic scene perception and congnition understanding.

---

Traffic scene understanding from Unmanned Aerial Vehicle (UAV) platforms plays a critical role in intelligent transportation systems due to its flexible deployment and wide-area monitoring capabilities. However, existing methods still face significant challenges in real-world traffic surveillance. The heavy reliance on optical images leads to severe performance degradation under adverse illumination conditions such as nighttime and fog. Meanwhile, current Visual Question Answering (VQA) models are limited to elementary perception tasks such as object counting and detection, lacking the domain-specific regulatory knowledge required to assess complex traffic behaviors. To address these limitations, we propose a novel Cross-spectral Traffic Cognition Network (CTCNet) for robust UAV traffic scene understanding. In particular, we design a Prototype-Guided Knowledge Embedding (PGKE) module that leverages high-level semantic prototypes from an external Traffic Regulation Memory (TRM) to anchor domain-specific regulatory knowledge into visual representations, enabling the model to comprehend complex traffic behaviors and distinguish fine-grained violation patterns. Moreover, we develop a Quality-Aware Spectral Compensation (QASC) module that exploits the complementary characteristics of optical and thermal modalities to perform bidirectional context exchange, selectively transferring discriminative features from the reliable modality to compensate for the degraded one for robust representation in complex environments. In addition, we construct Traffic-VQA, the first large-scale optical-thermal infrared (OPT-TIR) benchmark for UAV traffic understanding, comprising 8,180 well-aligned image pairs and 1.3 million question-answer pairs across 31 diverse question types covering both perceptual and cognitive tasks. Extensive experiments demonstrate that CTCNet significantly outperforms state-of-the-art methods, achieving notable improvements in both cognition and all-weather perception scenarios. The dataset is available at https://github.com/YuZhang-2004/UAV-traffic-scene-understanding.

<!-- <img src="Traffic-VQA.png" alt="Illustration of Traffic-VQA" style="zoom:67%;" /> -->


## 🌟 Key Features

* 🌍 **Massive Scale & Modality**: 8,180 meticulously aligned optical (RGB) and thermal infrared (TIR) image pairs, crucial for robust all-weather perception.

* 🧠 **Cognitive Depth**: Over 1.3 million question-answer pairs spanning 31 distinct question types (including 10 dedicated to complex cognitive reasoning like traffic rule violations).

* 💡 **CTCNet Framework**: Integrates an external Traffic Regulation Memory (TRM) to anchor domain-specific regulatory knowledge into visual representations.

## 📢 News

*   **[May, 2025]** Traffic-VQA dataset and annotations are now open-sourced on [🤗 Traffic-VQA](https://huggingface.co/datasets/YuYu2004/Traffic-VQA)!

## 🛠️ Methodology: CTCNet

Our Cross-spectral Traffic Cognition Network (CTCNet) systematically addresses the cognitive and perceptual bottlenecks of general MLLMs primarily focusing on the following two aspects:

Prototype-Guided Knowledge Embedding (PGKE): Retrieves high-level semantic prototypes from an offline Traffic Regulation Memory (TRM) to explicitly inject domain-specific traffic rules into the visual feature hierarchy.

Quality-Aware Spectral Compensation (QASC): Performs bidirectional context exchange between optical and thermal modalities. It selectively transfers discriminative features from the reliable modality (e.g., Thermal at night) to compensate for the degraded one (e.g., Optical at night).

## 🚀 Getting Started

1. **Download the Dataset**

Access the full Traffic-VQA dataset from [Hugging Face](https://huggingface.co/datasets/YuYu2004/Traffic-VQA).

2. **Installation & Evaluation**

    This repository contains:
    *   Annotation tools and scripts.
    *   Evaluation code (`evaluation.py`) to benchmark models on Traffic-VQA.

    To run the evaluation:
    ```bash
    python evaluation.py --model_names <your_model_name> --result_path <path_to_your_model_results.json> --device <cuda_device_id>
    ```
    Ensure your `result.json` file is formatted with "question", "pred", and "gt" keys for each sample.


## ✔️ Baselines & Evaluation

We evaluated several state-of-the-art multimodal models on Traffic-VQA. CTCNet establishes a new state-of-the-art, especially in complex cognitive tasks such as fine-grained traffic violation detection.

*   [GeoChat](https://huggingface.co/MBZUAI/geochat-7B)
*   [GeoPix](https://github.com/Norman-Ou/GeoPix)
*   [Falcon](https://huggingface.co/TianHuiLab/Falcon-Single-Instruction-Large)
*   [MiniCPM-V](https://huggingface.co/openbmb/MiniCPM-V)
*   [MiniGPT-v2](https://huggingface.co/spaces/Vision-CAIR/MiniGPT-v2)
*   [DeepSeek-VL](https://huggingface.co/deepseek-ai/deepseek-vl-7b-chat)
*   [Qwen2.5-VL](https://huggingface.co/Qwen/Qwen2.5-VL-7B-Instruct)
*   [Qwen3-VL](https://github.com/QwenLM/Qwen3-VL)
*   GPT 4o
*   Gemini 2.5 Flash
*   Gemini 2.5 Pro

## ✏️ Citation

<!-- If you find our dataset, code, or paper useful for your research, please consider citing:

@article{zhang2026uav,
  title={UAV traffic scene understanding: A cross-spectral guided approach and a unified benchmark},
  author={Zhang, Yu and Luo, Ze and Zhao, Zhicheng and Li, Chenglong and Tang, Jin},
  journal={ISPRS Journal of Photogrammetry and Remote Sensing},
  year={2026}
} -->


## 🤝 Acknowledgement

This work was supported in part by the National Natural Science Foundation of China (No. 62306005, 62006002, and 62076003), the Joint Funds of the National Natural Science Foundation of China (No. U20B2068), and the Natural Science Foundation of Anhui Province.
