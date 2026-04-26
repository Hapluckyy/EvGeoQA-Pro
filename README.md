# EvGeoQA-Pro: Evaluating Textual, Visual, and Agentic Geo-Spatial Reasoning in Foundation Models

> ⚠️ **Notice:** This paper is currently under peer review. The complete dataset, full multi-modal evaluation sets, sandbox environments, and source code will be fully open-sourced upon acceptance. **Currently, we provide dataset samples and framework details for reference.**

## Introduction

**EvGeoQA-Pro** is a comprehensive, multi-modal **Geo-Spatial Question Answering (GSQA) benchmark** designed to evaluate the reasoning and purpose-driven exploration capabilities of Foundation Models (LLMs and VLMs) within dynamic, real-world environments.


The benchmark establishes a comprehensive evaluation paradigm across **three distinct modalities**:
1. **Textual Context Reasoning:** Assesses factual discrimination and information synthesis within a self-contained localized text context.
2. **Multi-modal Visual-Textual Reasoning:** Evaluates the integration of heterogeneous information, requiring Vision-Language Models (VLMs) to synthesize map imagery with textual metadata.
3. **Autonomous Tool-use Agentic Reasoning:** Challenges models to interactively explore unknown geo-spatial spaces using tools over long-range contexts.

## Dataset Availability (Hugging Face)

We will host the full datasets and evaluation environments on Hugging Face. 

* 🤗 **[EvGeoQA-Pro Full QA Datasets (Link Pending Acceptance)](#)** * 🤗 **[EvGeoQA-Pro Sandbox Environments (Link Pending Acceptance)](#)** *Note: Links will be activated once the paper is officially accepted.*

## Evaluation Modalities & Examples

We have provided detailed examples for each of the three reasoning modalities evaluated in EvGeoQA-Pro. Please refer to the specific paths below:

- 📝 **[Textual Context Reasoning Example](./examples/textual_example.md)**
- 🗺️ **[Multi-modal Visual-Textual Reasoning Example](./examples/visual_example.md)**
- 🤖 **[Autonomous Tool-use Agentic Reasoning Example](./examples/agentic_example.md)**

*(Note: The above paths have been reserved. Detailed examples will be uploaded to these directories shortly.)*

## Dataset Statistics

The dataset covers three representative Chinese cities—Hangzhou (Provincial Capital), Qingdao (Regional Economic Hub), and Linyi (Prefecture-level City)—providing a hierarchical gradient of urban complexity.

| City | Charging Stations | User Locations | POI Categories | Total QA Pairs |
| :--- | :--: | :--: | :--: | :--: |
| **Hangzhou** | 258 | 997 | 25 | 19,940 |
| **Qingdao** | 165 | 995 | 23 | 14,162 |
| **Linyi** | 157 | 997 | 21 | 14,416 |

*Data Source: State Grid Corporation of China & Gaode(Amap) API.* ## Dataset Structure Example

Below is a sample entry from the **EvGeoQA-Pro** dataset. Each entry represents a unique query anchored to a specific user location, containing the natural language question, metadata, and a list of ground truth answers that satisfy both the charging necessity and co-located activity.

```json
{
    "Question_id": 1, 
    "Question": "I want to find a charging station and have a good meal at the same time. Can you recommend one for me?", 
    "Question_location": "Zhouquan Town, Tongxiang City, Jiaxing City, Zhejiang Province", 
    "Question_location_coord": [30.573871636176943, 120.37401098079212], 
    "Question_type": "advance", 
    "Question_poi": "Chinese Restaurant; Restaurant, Dining", 
    "Answer": [
        {
            "Station_id": "B0FFLC00X0", 
            "Station_name": "State Grid Zhejiang Hangzhou Linping District Century Park Charging Station", 
            "Station_coord": [30.440093, 120.304083], 
            "Distance": 16.27918236259536, 
            "Station_poi_type": "Dining Services; Chinese Restaurant; Specialty/Local Flavor Restaurant", 
            "Station_poi_name": "Shaxian Delicacies (Urban Harbor Branch)", 
            "correlation_measure": 0.9270795087435726
        }
        // ... (Additional ground truth stations omitted for brevity)
    ]
}
