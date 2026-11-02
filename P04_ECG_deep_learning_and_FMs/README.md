# P04 ECG deep learning and foundation models

Thursday 5 November, 13:00 to 16:00. Practical lead: Junjie Chen.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/junjiechen-chris/CDT-ECG-Lab2/blob/main/lab2-end-to-end.ipynb)

This practical follows Thursday's lecture on foundation models for time series.

| Part | Content |
|---|---|
| 1 | Preparing the data for three tasks |
| 2 | End-to-end classification: a ResNet on the raw ECG |
| 3 | Foundation model classification: ECGFounder |
| 4 | Beating the baselines |

The notebook, the code and the lab note are in Junjie's repository,
[CDT-ECG-Lab2](https://github.com/junjiechen-chris/CDT-ECG-Lab2), included here as the
submodule `CDT-ECG-Lab2/`. Read the
[lab note](https://github.com/junjiechen-chris/CDT-ECG-Lab2/blob/main/CDT_ECG_Lab_Resnet_FM.pdf)
alongside the notebook.

## Before the session

You do not need to install anything or download any data. Check that you can sign
in to [Google Colab](https://colab.research.google.com) with a Google account.

## In the session

1. Open the notebook with the **Open in Colab** button above, and save your own
   copy with **File > Save a copy in Drive**.
2. Choose a GPU: **Runtime > Change runtime type > T4 GPU**. The whole notebook
   takes about ten minutes on the free T4.
3. Run the Setup cell. It downloads the code, the data and the ECGFounder weights.
   Enter the data password when asked; your tutor will give it out during the
   session.
4. Run the cells in order and complete the four functions marked as tasks. Each
   is checked against a reference. If you have not finished a task, the notebook
   uses the reference instead, so the rest of the cells still run.
5. Submit the zip the notebook writes at the end to the leaderboard.

## Credits

- **Data:** PhysioNet/Computing in Cardiology Challenge 2017 (Clifford et al.,
  2017); PTB-XL (Wagner et al., 2020) and Chapman–Shaoxing (Zheng et al., 2020),
  CC-BY 4.0; Apnea-ECG (Penzel et al., 2000) and UCD St Vincent's (ODC-BY 1.0).
- **ECGFounder** (Li et al., PKUDigitalHealth), MIT licence.
- Sections 0 to 2 follow the Wearable Lab of the MSc in Applied Digital Health by
  Xiao Gu.
