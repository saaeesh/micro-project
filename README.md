# Email Spam Detection Using LSTM

Google Colab micro-project for classifying Enron emails as **spam** or **ham** with a Keras LSTM. Includes optional LSTM–GRU comparison inspired by the reference paper.

## Run
1. Open `Email_Spam_Detection_LSTM.ipynb` in [Google Colab](https://colab.research.google.com/).
2. Choose **Runtime → Run all** (CPU works; GPU may be faster).
3. The notebook downloads [Enron Spam Data on Kaggle](https://www.kaggle.com/datasets/marcelwiechmann/enron-spam-data) with `kagglehub`. If authentication is required, follow Kaggle's prompts.
4. Review EDA, training curves, confusion matrix, ROC-AUC and the email prediction example.
5. Optionally set `RUN_HYBRID=True` and rerun that cell for the comparison.

## Methods
80% train+validation / 20% held-out test, stratified; validation is 20% of training portion. Tokenizer fitted only to training data. Vocabulary 5000, padded sequence length 200 (reduced from paper's 600 for Colab convenience), embedding 64, LSTM 64, dense 64, dropout 0.5, sigmoid output, binary cross-entropy and Adam. Early stopping prevents needless epochs.

## Reference
Saleem, S. et al. (2025). *Spam Email Detection Using Long Short-Term Memory and Gated Recurrent Unit*. Applied Sciences, 15(13), 7407. https://doi.org/10.3390/app15137407

The paper uses an LSTM–GRU hybrid and reports approximately 90% accuracy. This notebook is a **simplified educational adaptation**, not an exact reproduction; its test metrics must be obtained by running the notebook. Dataset sizes and preprocessing may differ.

## GitHub upload
Create a new repository, then upload the notebook, README, requirements and `.gitignore`. Do not commit raw emails, trained models or secrets.
