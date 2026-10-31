# P03 EHR tokenisation strategies

Tuesday 3 November, 14:45 to 16:00. Practical lead: Pati Palo.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guxiao0822/CDT-HDS-ML-Time-Series/blob/main/P03_EHR_tokenisation/EHR_Tokenization_Lab.ipynb)

This practical builds on the earlier EHR preprocessing Lab. We will explore how clinical measurements can be represented as tokens and used by a Transformer to predict patient mortality. You will compare three tokenization strategies: Triplet, EIC, and Text Code, and experiment how different representations affect model performance.

| **Part** | **Content** |
|---|---|
| 1 | Convert clinical measurements into Triplet, EIC, and Text Code representations |
| 2 | Build embeddings for the different representations |
| 3 | Implement a Transformer for mortality prediction |
| 4 | Train and compare the three models using AUROC and AUPRC |

Follow the instructions and run the cells in order.

Before the session download data from Canvas.

In the session Open the notebook, Upload data , run the cells in order and complete the exercises.

The notebook can run on CPU, but a GPU may make training faster. 
The dataset is provided for teaching. Keep it within your own Colab session or Drive, and follow the course's data-sharing instructions.
