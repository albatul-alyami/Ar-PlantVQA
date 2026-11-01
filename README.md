# Ar-PlantVQA: An Arabic Mixture of Vision Experts Framework and Benchmark for Crop Disease Diagnosis
Ar-PlantVQA is an Arabic Visual Question Answering (VQA) dataset for plant disease diagnosis, comprising **10,290 question-answer pairs associated with 9,033 unique plant images**. The dataset is designed to support Arabic and multilingual vision-language research in the agricultural domain, covering nine question types across different levels of visual understanding and reasoning.

## Dataset Source and Construction

Ar-PlantVQA is derived from **PlantVillageVQA**, an English-language VQA dataset built upon PlantVillage images. PlantVillageVQA contains more than 193,000 expert-verified question-answer pairs covering 14 crops, 38 diseases, and nine question types.

Ar-PlantVQA was constructed by selecting a stratified subset of PlantVillageVQA to obtain a more balanced representation of question types. The selected English question-answer pairs were translated into Arabic using GPT-4o, followed by back-translation into English. Semantic similarity between the original and back-translated texts was assessed using Sentence-BERT, and samples meeting a similarity threshold of 0.80 were retained. The quality of the translated data was further assessed through human evaluation.

## Dataset Labels

Each sample consists of a plant image and its corresponding question-answer pair in both English and Arabic.

| Column | Description |
|---|---|
| `image_id` | Unique identifier of the image |
| `question_type` | One of the nine question categories |
| `question_en` | Question in English |
| `question_ar` | Question in Arabic |
| `answer_en` | Answer in English |
| `answer_ar` | Answer in Arabic |
| `image_path` | Relative path to the corresponding image |

### Question Types

The dataset includes nine question types organized into three cognitive levels:

**1. Foundational Perception**
- Existence & Sanity Check
- Plant Species Identification
- General Health Assessment

**2. Detailed Analysis**
- Visual Attribute Grounding
- Detailed Verification

**3. Higher-Order Reasoning**
- Specific Disease Identification
- Comprehensive Description
- Causal Reasoning
- Counterfactual Reasoning

The dataset includes two main answer types: **binary (Yes/No)** and **descriptive answers**, including short factual and free-text responses.

## Dataset Statistics

| Statistic | Value |
|---|---:|
| Total Question-Answer Pairs | 10,290 |
| Unique Images | 9,033 |
| Question Types | 9 |
| Answer Types | 2 |
| Average Question Length (Words) | 9.29 |
| Average Answer Length (Words) | 5.15 |
| Average Question Length (Tokens) | 36.63 |
| Average Answer Length (Tokens) | 20.11 |

### Dataset Splits

The dataset is divided into three **image-disjoint splits**, ensuring that no image appears in more than one split.

| Split | Question-Answer Pairs | Unique Images |
|---|---:|---:|
| Train | 7,375 | 6,478 |
| Validation | 811 | 719 |
| Test | 2,104 | 1,836 |
| **Total** | **10,290** | **9,033** |

## Dataset Download

The dataset is provided as three CSV files:

- `train.csv`
- `validation.csv`
- `test.csv`

The corresponding images are available as a compressed archive through GitHub Releases.

**[Download Images (images.zip)](https://github.com/albatul-alyami/Ar-PlantVQA/releases/download/v1.0.0/images.zip)**

After extracting the image archive, the dataset should be organized as follows:

```text
Ar-PlantVQA/
├── train.csv
├── validation.csv
├── test.csv
└── images/
    ├── image_001.jpg
    ├── image_002.jpg
    └── ...
```

The `image_path` column contains relative paths to the corresponding images.

## Citation

If you use Ar-PlantVQA in your research, please cite the associated publication once available and acknowledge the original PlantVillageVQA dataset.

## License

Please refer to the applicable licensing and redistribution terms of the original PlantVillage and PlantVillageVQA resources.
