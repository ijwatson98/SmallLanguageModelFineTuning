# Small Language Model Fine-Tuning

Experiments on supervised fine-tuning (SFT) and reinforcement learning from AI feedback (RLAIF) for smaller language models in a low-resource summarisation setup.

## Overview
This repository accompanies a project investigating whether smaller language models can be meaningfully improved for summarisation through:
- **supervised fine-tuning (SFT)**
- **reinforcement learning from AI feedback (RLAIF)**

The project compares checkpoints of:
- **T5**
- **BART**
- **GPT-2**

using the **XSum** summarisation dataset and **ROUGE-based evaluation**.

## Research question
Can smaller language models close some of the performance gap to larger models when trained in a low-resource setting using SFT and RLAIF?

## Main findings
- SFT produced clear performance gains over the base models.
- In the evaluation setup used here, RLAIF did not produce additional improvement over SFT.
- Smaller models improved substantially, but did not fully close the gap to stronger state-of-the-art systems.

## What this repo contains
- data preparation for summarisation experiments
- supervised fine-tuning workflows
- RLAIF training workflows
- evaluation notebooks for ROUGE-based comparison
- outputs and experiment artefacts used in the project analysis

## Models
This project focuses on smaller checkpoints of:
- T5
- BART
- GPT-2

## Data
- **Dataset:** XSum
- **Task:** one-sentence abstractive summarisation

## Typical experiment flow
1. run the model notebook for the model you want to evaluate
2. generate the corresponding outputs and metrics
3. use the final plotting notebook to compare results across models

## Setup

### 1. Clone the repository
```bash
git clone https://github.com/ijwatson98/SmallLanguageModelFineTuning.git
cd SmallLanguageModelFineTuning
```

### 2. Create an environment
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 3. Configure required credentials
If the RLAIF workflow depends on external model APIs or provider keys, add them to a local `.env` file or your shell environment before running experiments.

## Running the code
This repository is organised around notebooks. The recommended approach is to run the model notebooks separately, one per model, and then use the plotting notebook for final comparison.

### Notebook order
- `run_t5.ipynb`
- `run_bart_l.ipynb`
- `run_gpt2-m.ipynb`
- `plots.ipynb` — final results and comparison

Each model notebook contains the workflow for that model, including the relevant fine-tuning, RLAIF, evaluation, and output generation steps used in the project.

## Results
This repository supports the conclusion that:
- supervised fine-tuning is effective for smaller models in this setting
- in the evaluation setup used here, RLAIF did not produce additional improvement over SFT
- smaller models improved substantially, but did not fully close the gap to stronger state-of-the-art systems

## Scope
This is research code for a specific project, not a production training framework. The goal is experimental clarity rather than generality.

## Notes
This project was completed as a group project. Repository ownership and code hosting reflect the project setup rather than sole authorship of the overall work.
