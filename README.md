# Final Projects: Information Retrieval and Language Modeling

This repository contains the final project material for two NLP-related projects:

- The Information Retrieval project based on the ANTIQUE dataset;
- The Language Modeling project comparing small GPT-style models with different tokenisations.

Large files and generated artifacts are stored on Google Drive to keep the repository lightweight.

* [Google Drive Folder](https://drive.google.com/drive/folders/1Agz9DELaySgX9oJCNDqWZErU-JtFJ_iK?usp=drive_link)

## Projects

### 1. Information Retrieval: ANTIQUE Search Project

Notebook:

- `IR/IR_Antique_Search_Project.ipynb`


This project studies retrieval on the ANTIQUE dataset. It includes indexing/search experiments.

### 2. Language Modeling: GPT Language Model Project

Notebook:

- `LM_Project_GPTLanguageModel.ipynb`  
  Colab/Drive version: [notebook](https://drive.google.com/file/d/1w4pfqiuVtvRATnl5EwVRAqXjF8vcYVza/view?usp=drive_link)

External artifacts needed to run the LM notebook (also uploaded on the linked folder):

- `final_model_repository.zip`
- `parameter_study_artifacts.zip`

The Language Modeling project compares four GPT-style models trained on the same PG-19 book corpus:

- Character GPT
- Syllable GPT
- GPT-2 word/subword GPT
- Compact local-word GPT

The notebook loads the already trained best checkpoints from `final_model_repository.zip`, then recreates the final evaluation graphs and the parameter-study graphs from saved artifacts.

## Google Drive Artifacts

The Drive folder contains:

```text
LM_Project/
├── LM_Project_GPTLanguageModel.ipynb
├── final_model_repository.zip
└── parameter_study_artifacts.zip
```

The LM notebook expects this Drive layout when running in Colab:

```python
/content/drive/MyDrive/LM_Project/final_model_repository.zip
/content/drive/MyDrive/LM_Project/parameter_study_artifacts.zip
```

### `final_model_repository.zip`

This archive contains the expensive outputs of the final 100,000-iteration training runs. It is needed because the final notebook does not retrain the four large models from scratch in Colab. Instead, it reloads the trained weights and recomputes the evaluation tables, graphs, and generated samples from the saved files.

The most important part is `checkpoints/`. The `*_best_gpt.pt` files are the model states selected at the best validation loss, and these are the files used by the notebook when generating fresh text. 

### `parameter_study_artifacts.zip`

This archive contains the smaller hyperparameter-exploration results used in the notebook before the final selected models. It is needed so the parameter-study graphs can be recreated without rerunning all the temporary experiments.

## Reproducibility Notes

For the LM project, the expensive model training has already been completed. The final notebook is designed to load the trained checkpoints and saved parameter-study CSVs, so it can be rerun in Colab without retraining all final models.
