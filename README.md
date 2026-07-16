# DSPy + GEPA Translation Prompt Optimization

This repository contains a Google Colab notebook for setting up and validating a DSPy + GEPA translation prompt optimization pipeline.

## Features

- Install and validate DSPy
- Configure a Groq-hosted Llama 3.3 70B judge model
- Evaluate English → Cantonese and English → Mandarin translations
- Return translation scores and written feedback
- Perform RRWA (Reciprocal-Rank Weighted Aggregation) over 10 judge runs
- Run a small end-to-end GEPA optimization loop
- Export evaluation results and optimized program

## Requirements

- Google Colab
- Python 3.10+
- Groq API Key

## Installation

Run the first notebook cell or install manually:

```bash
pip install dspy==3.2.1 groq pandas numpy scipy tqdm
```

## API Setup

1. Create a Groq API key from https://console.groq.com/
2. Open the notebook in Google Colab.
3. Open **Secrets** from the left sidebar.
4. Create a secret named:

```
GROQ_API_KEY
```

5. Enable notebook access.

## Running the Notebook

Run the notebook from top to bottom.

The notebook will:

1. Install DSPy
2. Configure the Llama judge model
3. Evaluate five English → Cantonese examples
4. Evaluate five English → Mandarin examples
5. Run RRWA over 10 judge evaluations
6. Execute a GEPA optimization loop on five examples
7. Save the generated results

## Output Files

The notebook generates:

```
results/
├── environment.json
├── judge_results.csv
├── rrwa_results.json
└── optimized_program.json
```

## Project Structure

```
.
├── README.md
├── REPORT.md
├── requirements.txt
└── dspy_gepa_translation_setup.ipynb
```

## Technologies Used

- DSPy 3.2.1
- GEPA Optimizer
- Groq API
- Llama 3.3 70B
- Google Colab
- Python

## Notes

This notebook is intended as a reproducible setup and validation environment for DSPy and GEPA. Once a fine-tuned translation model is available, only the task model configuration needs to be updated while the judge, RRWA, and GEPA workflow can remain unchanged.
