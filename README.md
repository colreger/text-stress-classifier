# Fine-Tuning DistilBERT for Stress Classification in Text

Detecting signs of stress in English text by fine-tuning DistilBERT on Dreaddit. The task is binary classification of annotated Reddit text segments.

## Results from the original run

| Accuracy | Precision | Recall | F1 |
| ---: | ---: | ---: | ---: |
| 82.24% | 80.10% | 87.26% | 83.53% |

The epoch 3 checkpoint was evaluated on 715 examples, with 80 false positives and 47 false negatives. Precision, recall and F1 are for the stress label. The original run evaluated the supplied test split after each epoch, so these figures describe development performance. An independent final evaluation would require a separate validation split for model selection.

## Run the notebook

Use Python 3.13. From the repository root, install the dependencies and launch JupyterLab.

```bash
python -m pip install -r requirements.txt
jupyter lab train.ipynb
```

Run the notebook cells in order. The first run downloads the dataset and pretrained model. The portfolio notebook uses the original training hyperparameters and trains for three epochs on all 2,838 training examples. It evaluates the test split after training. The notebook reports aggregate metrics and confusion counts. Checkpoints are written locally to `results/`.

The [Dreaddit dataset card](https://huggingface.co/datasets/andreagasparini/dreaddit) describes the source data and annotations.
