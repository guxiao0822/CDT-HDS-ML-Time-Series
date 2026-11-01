# P01 ECG signal processing

Monday 2 November, 13:00 to 16:00. Practical lead: Junjie Chen.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/junjiechen-chris/CDT-HDS-ECG-Lab-1/blob/main-v2/ECG_Preprocessing.ipynb)

This practical follows Monday's lecture on biomedical signal processing. It goes
through basic signal processing algorithms, using the ECG as an example. You will
derive heart rate and heart rate variability from the R peaks derived by an
established toolbox (NeuroKit2), build your own beat detector step by step and
compare it with NeuroKit2, then use ECG features to train a classifier that
distinguishes four rhythm classes (normal rhythm, atrial fibrillation, other
rhythms and noisy recordings).

| Part | Content |
|---|---|
| 1 | What is an ECG signal? Label the P, Q, R, S and T waves |
| 2 | Measuring rhythm: heart rate, SDRR and RMSSD from the R peaks found by NeuroKit2 |
| 3 | Locating R peaks: a beat detector built step by step, compared with NeuroKit2 |
| 4 | Classifying rhythms: a RandomForest on 54 ECG features |

The notebook and the lab note are in Junjie's repository,
[CDT-HDS-ECG-Lab-1](https://github.com/junjiechen-chris/CDT-HDS-ECG-Lab-1/tree/main-v2). Read the
[lab note](https://github.com/junjiechen-chris/CDT-HDS-ECG-Lab-1/blob/main-v2/CDT_Healthcare_Data_Science_ML_for_Time_Series_Module.pdf)
alongside the notebook. 

## Before the session

You do not need to install anything or download any data. Check that you can sign
in to [Google Colab](https://colab.research.google.com) with a Google account.

## In the session

1. Open the notebook with the **Open in Colab** button above, and save your own
   copy with **File > Save a copy in Drive**.
2. Run the Setup cell. It downloads the code and data and installs the packages.
   Enter the data password when asked; your tutor will give it out during the
   session.
3. Run the cells in order and complete the cells marked **YOUR CODE**. Each task
   is checked against a reference. If you have not finished a task, the notebook
   uses the reference instead, so the rest of the cells still run.

A CPU runtime is enough. Keep your test macro F1 from Part 4: Practical 04 trains
neural networks on the same recordings and the same split, and compares them with
it.

## Credits

- **Data:** PhysioNet/Computing in Cardiology Challenge 2017 (Clifford et al.,
  Computing in Cardiology, 2017).
- **NeuroKit2** (Makowski et al., Behavior Research Methods, 2021) supplies the
  reference beats and the ECG features.
- The practical is adapted from the CWM Wearable Technology practical by Mauricio
  Villarroel, with detector material credited to Gari Clifford and Mauricio
  Villarroel.
