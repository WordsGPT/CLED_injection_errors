# CLED_injection_errors

This repository contains the code and models for classifying errors injected into NLP models (such as OPUS and T5) under different precision formats (FP16 and FP32).

## Datasets

The datasets used in this project are based on CNN and IWSLT2017. They include fault-free predictions and predictions with single bit-flip fault injections.

Download the datasets from [Zenodo](https://zenodo.org/records/10647624) and place them in the `datasets/` directory.

The `datasets/` directory should contain:
- `cnn_input_text.txt`
- `cnn_output_predict_fault_free.txt`
- `cnn_output_predict_single_fi_bit_100times.txt`
- `cnn_output_reference.txt`
- `iwslt2017_input_text.txt`
- `iwslt2017_output_predict_fault_free.txt`
- `iwslt2017_output_predict_single_fi_bit_100times.txt`
- `iwslt2017_output_reference.txt`

## Models and Notebooks

The `models/` directory contains Jupyter notebooks for training and evaluating the error classification models, as well as the saved model pipelines.

### Notebooks
- `classificator_opus_FP16.ipynb`: Classifier for OPUS model with FP16 precision.
- `classificator_opus_FP32.ipynb`: Classifier for OPUS model with FP32 precision.
- `classificator_opus_FP16_eval_with_FP32.ipynb`: Evaluation of OPUS FP16 classifier using FP32 data.
- `classificator_t5_FP16.ipynb`: Classifier for T5 model with FP16 precision.
- `classificator_t5_FP32.ipynb`: Classifier for T5 model with FP32 precision.
- `classificator_t5_FP16_eval_with_FP32.ipynb`: Evaluation of T5 FP16 classifier using FP32 data.
- `classificator_t5Andopus_FP32.ipynb`: Combined classifier for T5 and OPUS models with FP32 precision.

### Saved Models
- `pipeline_opus_model.joblib`: Pre-trained pipeline model for OPUS.
- `pipeline_t5_model.joblib`: Pre-trained pipeline model for T5.

## Directory Structure

- `datasets/`: Contains the input texts and model predictions (fault-free and with injected faults).
- `models/`: Contains the Jupyter notebooks for data processing and model training, along with the saved `.joblib` models.
- `figs/`: Directory for saving generated figures and plots.
- `backup_df_saved/`: Directory for saving backup dataframes during processing.

## Requirements

The notebooks require several Python libraries, including:
- `pandas`
- `numpy`
- `nltk`
- `scikit-learn`
- `matplotlib`
- `seaborn`
- `joblib`
- `openpyxl`

You can install the required packages using pip:
```bash
pip install pandas numpy nltk scikit-learn matplotlib seaborn joblib openpyxl
```

## Usage

1. Clone the repository.
2. Download the datasets from Zenodo and place them in the `datasets/` folder.
3. Install the required dependencies.
4. Open and run the Jupyter notebooks in the `models/` directory to train or evaluate the classifiers.