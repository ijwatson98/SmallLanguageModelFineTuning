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
- evaluation scripts / notebooks for ROUGE-based comparison
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
1. prepare and filter the dataset
2. run baseline model evaluation
3. fine-tune the model with supervised learning
4. evaluate the fine-tuned checkpoint
5. initialise the RLAIF stage from the SFT checkpoint
6. run RLAIF
7. evaluate the final checkpoint and compare results

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
This repository was developed for a project workflow rather than as a packaged library, so the exact entry points depend on the scripts or notebooks you want to run.

Recommended order:
1. run data preparation
2. run baseline / SFT training
3. run evaluation
4. run RLAIF
5. run final evaluation and result comparison

Replace the placeholders below with the actual entry points used in the repo:

```bash
python <prepare_data_script>.py
python <run_sft_script>.py
python <evaluate_script>.py
python <run_rlaif_script>.py
python <evaluate_script>.py
```

## Results
This repository supports the conclusion that:
- supervised fine-tuning is effective for smaller models in this setting
- RLAIF is not automatically beneficial, and depends strongly on the training and evaluation setup

## Scope
This is research code for a specific project, not a production training framework. The goal is experimental clarity rather than generality.

## Notes
This project was completed as a group project. Repository ownership and code hosting reflect the project setup rather than sole authorship of the overall work.
