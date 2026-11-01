# P02 EHR preprocessing and basic modelling

Tuesday 3 November, 13:00 to 14:15. Practical lead: Yujiang Wang.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/guxiao0822/CDT-HDS-ML-Time-Series/blob/main/P02_EHR_preprocessing/P02_EHR_preprocessing_lab.ipynb)

In this practical, we will predict in-hospital mortality from the first 48 hours of
ICU data, using an EHR dataset in which some measurements are missing. We first find
the missing values and fill them in, and then compare two classical models on summary
features with the three sequence models from the morning's lecture: an LSTM, a TCN
and a Transformer.

| Part | What we do |
|---|---|
| 1 | Find the missing values, write two imputers (mean, and last observation carried forward), and compare them on values that we hide ourselves |
| 2 | Summary features, normalisation without leakage, logistic regression and a random forest |
| 3 | The sequence models from the lecture: an LSTM that you unroll over time, a TCN (causal and dilated convolutions) and a Transformer encoder (self-attention) |
| 4 | Compare all the models, with bootstrap confidence intervals |

The cells marked TODO are for you to complete, and each one is followed by a few
checks that print PASS or FAIL. If you finish early, there are some extensions at
the end.

## Before the session

Please check your set-up before the session; it takes about 5 minutes.

1. Make sure you can sign in to [Google Colab](https://colab.research.google.com)
   with a Google account.
2. Open the notebook with the Open in Colab button above, and run the three cells
   under *Set-up*, in order:
   - the environment check prints the version of each package, and installs
     anything that is missing;
   - the imports cell loads the packages and defines a few helper functions;
   - the data cell downloads `EHR_data.zip` (about 10 MB) from Google Drive, asks
     for the data password, and unzips the data. You can find the password on
     Canvas, on the [HDS-M04: Module Info](https://canvas.ox.ac.uk/courses/298593/pages/hds-m04-module-info-machine-learning-for-time-series-2026?module_item_id=3212983)
     page, in the section "Practical 2 – EHR Preprocessing and Basic Modelling" (or
     simply search the page for "passcode"). If it does not work, ask a tutor for
     the password.

   If all three run without an error, you are ready. This is the recommended way to
   do this lab; the P.S. notes at the end are only for reference.

## In the session

1. Open the notebook with the Open in Colab button above, and make sure you save
   your own copy of it in your Google Drive (*File > Save a copy in Drive*). Work in
   that copy; otherwise your changes will be lost when the Colab session ends.
2. You do not need a GPU: the whole notebook runs on a CPU in a few minutes.
3. Run the cells in order.

P.S. If the download fails, download `EHR_data.zip` in your browser, from
[Google Drive](https://drive.google.com/file/d/1obrZjLQAyx0iJXuGusKGUUTpaIfrXGd_/view?usp=sharing)
or from [Canvas](https://canvas.ox.ac.uk/courses/298593/files/9308218?wrap=1),
and then either

- drag it into the *Files* panel in Colab (the folder icon on the left) and re-run
  the data cell; or
- put it, still zipped, at `MyDrive/cdt_ehr_lab/EHR_data.zip` in your Google Drive,
  set `USE_MY_DRIVE = True` in the data cell, and re-run it. Colab will ask for
  access to your Drive; sign in with the account that has the zip.

P.S. If you want to use your own Python environment instead of Colab (we do not
recommend this for the session), you can create one with conda and start Jupyter in
the folder with the notebook:

```bash
conda create -n ehr-lab python
conda activate ehr-lab
pip install numpy pandas matplotlib scikit-learn imbalanced-learn torch gdown pyzipper jupyter
jupyter notebook
```

The data cell unzips the data into an `EHR_data/` folder next to the notebook. If
the download fails, put `EHR_data.zip` next to the notebook yourself and keep it
zipped: the notebook unzips it with the password, and your computer's own unzip tool
may not be able to open it.

The dataset is provided for teaching only. Please keep it in your own Drive and
Colab session, and do not upload it anywhere else.
