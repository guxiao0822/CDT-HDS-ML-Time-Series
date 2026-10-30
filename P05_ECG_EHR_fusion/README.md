# P05 ECG and EHR fusion

Friday 6 November, 13:00 to 14:15. Practical lead: Edward Phillips.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guxiao0822/CDT-HDS-ML-Time-Series/blob/main/P05_ECG_EHR_fusion/fusion_lab.ipynb)

This practical follows Thursday's lecture on multimodal and agentic AI for time
series. You will align 12-lead ECGs with their reports in a shared space, then
combine ECGs with EHR data from the same patients (age, sex and recent blood
tests) to predict 1-year mortality, and find out where and how fusing them helps.

| Part | Content |
|---|---|
| 1 | Contrastive (CLIP-style) training of a small ECG encoder, compared with a pretrained ECG foundation model |
| 2 | 1-year mortality from each modality on its own, with bootstrap confidence intervals |
| 3 | Fusion: early against late, then intermediate fusion with concatenation, addition, gating and attention |
| 4 | A quick check on when the features were recorded |

Cells marked **TODO** must be completed before the cells after them will run.
Each TODO is followed by checks that print PASS or FAIL. There are extensions at
the end for anyone who finishes early.

## Before the session

1. **Register on PhysioNet.** The data is derived from MIMIC-IV and MIMIC-IV-ECG,
   which needs PhysioNet credentialed access and a signed data use agreement for
   MIMIC-IV. Xiao Gu will ask you to register on Monday 2 November.
2. **Download `cdt_fusion_lab_data.zip` from Canvas** (63 MB).
3. **Put the zip in Google Drive** at `MyDrive/cdt_fusion_lab/cdt_fusion_lab_data.zip`.
   Create the `cdt_fusion_lab` folder at the top level of My Drive, and leave the
   zip zipped: the notebook unzips it for you.

## In the session

1. Open the notebook with the **Open in Colab** button above, and save your own
   copy with **File > Save a copy in Drive**.
2. Switch to a GPU with **Runtime > Change runtime type > T4 GPU**. Without a GPU
   the notebook still runs, but Part 1 trains for fewer epochs.
3. Run the cells in order. The first data cell asks to connect to Google Drive:
   sign in with the account that holds the zip, and allow access.

Keep the data in your own Drive and Colab session. Do not upload it anywhere
else, share it with anyone who is not credentialed, or paste any of it into an AI
chatbot.

## Credits

- **Data:** MIMIC-IV-ECG (Gow et al., PhysioNet, https://doi.org/10.13026/4nqg-sb35)
  and MIMIC-IV (Johnson et al., PhysioNet).
- **ECGFounder** (PKUDigitalHealth, NEJM AI 2025, MIT licence) supplies the
  pretrained ECG embeddings, and **BioLinkBERT** the report embeddings.
- The Part 1 set-up follows Jinpei Han's contrastive ECG and text pipeline (MIT
  licence).
