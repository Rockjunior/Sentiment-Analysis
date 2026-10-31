# SentimentScope

SentimentScope is a PyTorch-based natural language processing project for
binary sentiment classification of IMDB movie reviews. The project uses a
transformer architecture and `bert-base-uncased` tokenization to classify
reviews as positive (`1`) or negative (`0`).

The complete workflow is provided in the
[`SentimentScope_starter.ipynb`](project/SentimentScope_starter.ipynb) notebook.
It covers dataset exploration, preprocessing, PyTorch data loading, model
construction, training, validation, checkpointing, and final evaluation.

## Project goals

- Prepare and explore the IMDB review dataset.
- Build a custom PyTorch `Dataset` and `DataLoader`.
- Adapt a transformer model for binary classification.
- Train and validate the model using CPU or CUDA when available.
- Evaluate the best checkpoint on the held-out test set.
- Work toward a test accuracy above 75%.

## Repository structure

```text
.
├── project/
│   ├── SentimentScope_starter.ipynb  # Main notebook
│   ├── requirements.txt              # Python dependencies
│   └── aclImdb_v1.tar.gz             # IMDB dataset archive
└── README.md
```

## Getting started

### 1. Clone the repository

```bash
git clone https://github.com/Rockjunior/Sentiment-Analysis.git
cd Sentiment-Analysis
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

Install the requirements from the `project` directory:

```bash
python -m pip install -r project/requirements.txt
```

### 4. Run the notebook

Start Jupyter from the project directory:

```bash
cd project
jupyter notebook
```

Open `SentimentScope_starter.ipynb` and run the cells in order. The notebook
extracts `aclImdb_v1.tar.gz` into the project directory before loading the
training and test reviews. The first run may also download the
`bert-base-uncased` tokenizer from Hugging Face.

## Model evaluation

During training, the notebook saves the best validation checkpoint as
`sentimentscope_best.pt`. After training, it reloads that checkpoint and
evaluates it once on the test set, reporting accuracy and whether the 75%
target was met.

## Dataset

This project uses the [IMDB Large Movie Review Dataset](https://ai.stanford.edu/~amaas/data/sentiment/).
The archive is included in `project/aclImdb_v1.tar.gz` and contains labeled
positive and negative reviews for training and testing.

## License and attribution

The IMDB dataset is provided by
[Stanford AI](https://ai.stanford.edu/~amaas/data/sentiment/). Review its
original terms before redistributing the dataset or derived artifacts.
