# PAIRadox — Intel Scene Classification

## Objective

Build a six-class scene classification model for the Intel-Scene dataset under the hackathon rules, using a ResNet-18 trained from scratch.

## Dataset

The project uses the provided Intel-Scene training and validation datasets, covering six scene classes:

- Buildings
- Forest
- Glacier
- Mountain
- Sea
- Street

The hidden test set is used only to generate predictions for submission.

## Methodology

1. Register the dataset tables in 3LC.
2. Inspect examples and verify labels before adding labeled rows.
3. Use the permitted labeling budget and maintain the required 3LC project history.
4. Train ResNet-18 from random initialization using CPU-only training.
5. Evaluate the model on the provided validation dataset.
6. Generate predictions for the hidden test dataset using `predict.py`.
7. Save the generated predictions in the required submission format.

## Recorded Validation Results

**Best recorded validation accuracy: 84.33% (1,012/1,200 correct).**

- Architecture: ResNet-18
- Initialization: Random initialization; no pretrained weights
- Training duration: 20 epochs
- Random seed: 42
- Learning-rate scheduler: CosineAnnealingLR
- Training device: CPU
- Labeling budget at the start of this run: 2,977/3,000 weight-1 rows

The best validation accuracy was recorded at epoch 16 and again at epoch 19. The final epoch achieved 84.17%.

These are validation results, not hidden-test accuracy or leaderboard results.

## Observations

The validation accuracy improved over the earlier recorded result of 80.08%, reaching 84.33% in the 20-epoch run.

Earlier evaluations showed that forest and street were relatively strong classes, while glacier and mountain were frequently confused with each other. Buildings and street also showed notable confusion. These observations should be checked against the latest run's class-wise metrics before being treated as final findings.

## Project Files

- `register_tables.py` — registers dataset tables with 3LC.
- `train.py` — trains and evaluates the model.
- `predict.py` — generates hidden-test predictions.
- `config.yaml` — project configuration.
- `sample_submission.csv` — provided submission template.
- `submission.csv` — generated test predictions.
- `screenshots/` — screenshots of the 3LC table lineage, embeddings, run metrics, and training result.
- `submission-assets/Intel-Scene-3LC-parts/` — split parts of the 3LC project archive.

## Reproducibility and Verification

The repository includes the training and prediction code, recorded validation results, screenshots, and split 3LC project archive for inspection.

Reassemble the archive parts in numerical order before opening the ZIP. The 3LC project history and screenshots provide evidence for inspecting the dataset tables, labeling workflow, and training results.

## Compliance

The project is intended to follow the hackathon restrictions on training data, labeling budget, model initialization, and hidden-test usage. The 3LC archive and screenshots should be used to verify the labeling workflow and project history.
