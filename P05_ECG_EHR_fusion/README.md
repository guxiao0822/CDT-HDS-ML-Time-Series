# P05 ECG and EHR fusion

Friday 6 November, 13:00 to 14:15. Practical lead: Edward Phillips.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guxiao0822/CDT-HDS-ML-Time-Series/blob/main/P05_ECG_EHR_fusion/fusion_lab.ipynb)

This practical follows Thursday's lecture on multimodal and agentic AI for time
series. You will align 12-lead ECGs with their reports in a shared space, then
combine ECGs with EHR data (age, sex and recent blood tests) to predict 1-year
mortality, and find out where and how fusing them helps.

The ECGs and their machine reports are real, from the open MIMIC-IV-ECG release.
The EHR and the outcome are simulated, so no PhysioNet credentials are needed.

| Part | Content |
|---|---|
| 1 | Contrastive (CLIP-style) training of a small ECG encoder, compared with a pretrained ECG foundation model |
| 2 | 1-year mortality from each modality on its own, with bootstrap confidence intervals |
| 3 | Fusion: early against late, then intermediate fusion with concatenation, addition, gating and attention |
| 4 | A quick check on when the features were recorded |

Cells marked **TODO** are for you to complete. Each starts with a placeholder, so
the notebook runs from top to bottom, and is followed by tests that report FAILED
until your code is right. There are extensions at the end for anyone who finishes
early, starting with a challenge: build the best model you can and score it on 500
held-out patients.

## Before the session

1. **Download `cdt_fusion_lab_data.zip` from Canvas** (92 MB).
2. **Put the zip in Google Drive** at `MyDrive/cdt_fusion_lab/cdt_fusion_lab_data.zip`.
   Create the `cdt_fusion_lab` folder at the top level of My Drive, and leave the
   zip zipped: the notebook unzips it for you.

## In the session

1. Open the notebook with the **Open in Colab** button above, and save your own
   copy with **File > Save a copy in Drive**.
2. Switch to a GPU with **Runtime > Change runtime type > T4 GPU**. Without a GPU
   the notebook still runs, but Part 1 trains for fewer epochs.
3. Run the cells in order. The first data cell asks to connect to Google Drive:
   sign in with the account that holds the zip, and allow access.

Please keep the data to this module, and do not paste any of it into an AI chatbot.
It is shared under the Open Database License (ODbL), as MIMIC-IV-ECG is: if you
share anything built from it, keep the attribution and the licence.

## Credits

- **Data:** 1,000 ECGs and machine reports (plus 500 for the challenge) from
  MIMIC-IV-ECG (Gow et al., PhysioNet, open access, ODbL,
  https://doi.org/10.13026/4nqg-sb35). The EHR and outcomes are simulated; no
  MIMIC-IV data is used.
- **ECGFounder** (PKUDigitalHealth, NEJM AI 2025, MIT licence) supplies the
  pretrained ECG embeddings, and **BioLinkBERT** the report embeddings.
- The Part 1 set-up follows Jinpei Han's contrastive ECG and text pipeline (MIT
  licence).
