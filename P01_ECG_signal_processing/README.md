# P01 ECG signal processing

Monday 2 November, 13:00 to 16:00. Practical lead: Junjie Chen.

[Open in Colab](https://colab.research.google.com/github/junjiechen-chris/CDT-HDS-ECG-Lab-1/blob/main/ECG_Preprocessing.ipynb)

The lab lives in its own repository, https://github.com/junjiechen-chris/CDT-HDS-ECG-Lab-1, included here as the submodule `CDT-HDS-ECG-Lab-1`. Read the lab note, `note/Lab1_Lab_Note.pdf`, alongside the notebook `ECG_Preprocessing.ipynb`. Both follow the same four questions, from the raw ECG waveform to interpretable rhythm features and a classifier. Every task is a function written from its specification and checked against a reference implementation.

| **Part** | **Content** |
|---|---|
| 1 | What is an ECG signal? Label the P, Q, R, S and T waves on excerpts from normal recordings |
| 2 | Measure heart rate, SDRR and RMSSD from RR sequences |
| 3 | Code a naive beat detector, grow it into a QRS-searching detector step by step, and score it against NeuroKit2 on about 2,000 recordings |
| 4 | Train and evaluate a RandomForest classifier on 54 NeuroKit2 features; keep the test macro F1 for P04 |

Open the notebook in Colab, save a copy in Drive, and run the Setup cell. It clones the lab repository, installs the requirements and downloads the data zip. The zip password is given in the session.

A CPU runtime is enough. The whole notebook runs in about ten minutes.

The data are 2,000 single-lead recordings from the PhysioNet/CinC Challenge 2017, provided for teaching; keep them within your own Colab session or Drive and respect the dataset's terms. To get the files locally, clone with `git clone --recurse-submodules`.
