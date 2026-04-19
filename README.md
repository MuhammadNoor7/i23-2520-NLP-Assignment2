# CS-4063 Assignment 2 - Neural NLP Pipeline

This repository contains my submission for CS-4063 Natural Language Processing Assignment 2.

## Repository Link

Public repository: https://github.com/MuhammadNoor7/i23-2520-NLP-Assignment2

## Contents

- `i23-2520_Assignment2_DS-A.ipynb` - main notebook with Parts 1, 2, and 3
- `i23-2520_Assignment2_DS_A.pdf` - final report PDF
- `cleaned.txt` - cleaned BBC Urdu corpus
- `raw.txt` - raw corpus used for ablation and comparison
- `metadata.json` - article metadata and labels
- `data/` - annotated sequence-labeling data
- `embeddings/` - saved embedding artifacts
- `models/` - saved trained model checkpoints

## Folder Structure

```text
i23-2520_Assignment2_DS-A/
|-- i23-2520_Assignment2_DS-A.ipynb
|-- i23-2520_Assignment2_DS_A.pdf
|-- cleaned.txt
|-- raw.txt
|-- metadata.json
|-- data/
|   |-- pos_train.conll
|   |-- pos_test.conll
|   |-- ner_train.conll
|   |-- ner_test.conll
|-- embeddings/
|   |-- tfidf_matrix.npy
|   |-- ppmi_matrix.npy
|   |-- embeddings_w2v.npy
|   |-- word2idx.json
|-- models/
    |-- bilstm_pos.pt
    |-- bilstm_ner.pt
    |-- transformer_cls.pt
```

## Setup and Run

This submission is self-contained. All executable code is in the notebook, so no extra `.py` scripts are needed to reproduce the results.

1. Open the assignment folder in VS Code or Jupyter.
2. Confirm these input files are present in the repository root:
    - `cleaned.txt`
    - `raw.txt`
    - `metadata.json`
3. Open `i23-2520_Assignment2_DS-A.ipynb`.
4. Select the Python kernel used for the assignment environment.
5. Run all notebook cells from top to bottom without skipping sections.
6. Wait for the notebook to finish saving outputs for Parts 1, 2, and 3.
7. Check that the generated artifacts appear in the output folders:
    - `data/`
    - `embeddings/`
    - `models/`
8. Verify the final notebook outputs include the expected tables, figures, and metrics.
9. Submit `i23-2520_Assignment2_DS_A.pdf` together with the notebook and repository contents.

## What To Run

Run only `i23-2520_Assignment2_DS-A.ipynb`. The notebook loads the input files, trains or evaluates the models, and writes the generated artifacts into `data/`, `embeddings/`, and `models/`. No separate script entry point is required.

The PPMI matrix at `embeddings/ppmi_matrix.npy` is a generated artifact and is very large. If you are uploading through GitHub's web interface, do not try to upload that file manually. Recreate it by running Part 1 of the notebook instead.

## Reproduce Each Part

### Part 1: Distributional Word Representations

Run the Part 1 cells in the notebook to regenerate the cleaned corpus processing, TF-IDF matrix, PPMI matrix, skip-gram embeddings, nearest-neighbor examples, analogy evaluation, and MRR comparison tables.

### Part 2: POS Tagging and NER

Run the Part 2 cells to rebuild the POS and NER datasets, train the BiLSTM models, evaluate the frozen and fine-tuned settings, and reproduce the ablation, confusion matrix, and error analysis outputs.

### Part 3: Transformer Topic Classification

Run the Part 3 cells to train the custom Transformer classifier, reproduce the attention visualizations, confusion matrix, training curves, and the comparison against the BiLSTM baseline.

If you want to rerun only one section, execute the notebook cells for that section after the required earlier inputs or saved artifacts are available. For a full reproduction, run the notebook from the first cell to the last cell.

## Notes

- All core components are implemented from scratch using PyTorch and NumPy.
- Built-in transformer modules such as `nn.Transformer`, `nn.MultiheadAttention`, and `nn.TransformerEncoder` are not used.
- The notebook includes Part 1 embedding experiments, Part 2 POS/NER experiments, and Part 3 Transformer topic classification.
- The large `embeddings/ppmi_matrix.npy` file is intentionally treated as a generated output and should be reproduced from the notebook rather than uploaded by hand.

## Submission Checklist

- [ ] Notebook opens successfully
- [ ] Required input files are present
- [ ] Notebook runs from top to bottom
- [ ] Outputs for Parts 1, 2, and 3 are visible
- [ ] Report PDF is included
- [ ] `cleaned.txt`, `raw.txt`, and `metadata.json` are included
- [ ] `data/`, `embeddings/`, and `models/` folders are included
- [ ] Repository is public
- [ ] Repository name matches the assignment requirement
- [ ] At least 5 meaningful commits
- [ ] README is present
