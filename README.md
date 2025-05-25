# Finetuning a Danish Language Model for Grammatical Error Correction

This project demonstrates the fine-tuning of a pre-trained Danish language model for the task of **grammatical error correction**. Specifically, we use the `ufal/byt5-small-multilexnorm2021-da` model and train it to improve upon noisy or informal Danish text inputs.  

The repository includes:
- An interactive notebook for data preparation, model training, and evaluation.
- A dataset of noisy/corrected word pairs (`data.txt`).
- A PDF report and poster summarizing the project findings and methodology.

---

## 📁 Files

- `Finetuning-Danish-LLM.ipynb` – Google Colab notebook for model training and evaluation.
- `report.pdf` – Project report describing dataset, methods, results, and discussion.
- `poster.pdf` – Visual summary of the project for presentation purposes.
- `data.txt` – Dataset of token-level noisy/correct word pairs used for training and evaluation.

---

## 🧠 Methodology

1. **Dataset Preparation**  
   Input data is preprocessed into span-masked sequences using `<extra_id_0>` and `<extra_id_1>` to guide the model in correcting specific tokens.

2. **Baseline Evaluation**  
   A word error rate (WER) baseline is computed using naive uncorrected input.

3. **Model Fine-tuning**  
   The model is trained using `PyTorch Lightning`, `HuggingFace Transformers`, and GPU acceleration (Colab/Tesla K80).

4. **Evaluation**  
   We compare the WER across three systems:
   - Baseline (no correction)
   - Untrained model
   - Fine-tuned model

   Results show a significant improvement with training:
   ```
   Baseline WER:        1.009
   Untrained model WER: 1.001
   Trained model WER:   0.348
   ```

---

## 📦 Requirements

Install dependencies in Colab or your environment:
```bash
pip install torch==1.10.0+cu111
pip install torchmetrics==0.4.1
pip install transformers==4.8.2
pip install pytorch_lightning==1.3.8
pip install Levenshtein
```

---

## 🚀 Usage

To run the notebook:
1. Clone the repository and upload it to [Google Colab](https://colab.research.google.com/).
2. Upload your own `data.txt` or use the provided one.
3. Run all cells in `Finetuning-Danish-LLM.ipynb` to reproduce training and evaluation.

---

## 📝 Citation

If you use this project or dataset, please cite the associated report or credit this repository.

---

## 📍 Acknowledgements

- Model: [`ufal/byt5-small-multilexnorm2021-da`](https://huggingface.co/ufal/byt5-small-multilexnorm2021-da)
- Project developed as part of a course/research project on Danish NLP.
