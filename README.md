#  Indian Name Generator using RNN, BLSTM & Attention

This project implements deep learning models to generate realistic Indian names using character-level sequence modeling. It compares Vanilla RNN, Bidirectional LSTM (BLSTM), and Attention-based RNN.

---

##  Project Structure

```
.
├── TrainingNames.txt
├── nluprob2.py
└── README.md
```

---

##  Requirements

Make sure Python (3.8–3.11 recommended) is installed.

Install dependencies:

```
pip install torch torchvision torchaudio
```

---

##  How to Run

1. Place your dataset file in the same directory:

   ```
   TrainingNames.txt
   ```

   (Ensure one name per line)

2. Run the script:

   ```
   python nluprob2.py
   ```

---

##  What the Code Does

###  Task 0: Data Cleaning

* Converts names to lowercase
* Removes non-alphabetic entries
* Filters names with length < 3
* Removes duplicates
* Limits dataset to 1000 names

---

###  Task 1: Model Training

Implements three models:

* Vanilla RNN
* BLSTM (Bidirectional LSTM)
* Attention-based RNN

Each model:

* Learns character-level patterns
* Generates new names using sampling

---

###  Task 2: Evaluation Metrics

Evaluates generated names using:

* **Novelty** → Fraction of generated names not in training set
* **Diversity** → Ratio of unique generated names
* **Realism Score** → Based on heuristic rules (length, vowels, repetition)

---

##  Output

The script prints:

* Training loss per epoch
* Number of parameters in each model
* Generated name samples
* Evaluation metrics (Novelty, Diversity)
* Realism scores
* Failure cases and analysis

---

##  Example Output

```
RNN -> Novelty: 0.85, Diversity: 0.78
BLSTM -> Novelty: 0.91, Diversity: 0.84
Attention -> Novelty: 0.88, Diversity: 0.81
```

---

##  Notes

* Automatically uses GPU if available
* You can tune:

  * `EPOCHS`
  * `HIDDEN`
  * `EMBED`
  * `temperature` (controls randomness in generation)

---

##  Author

Sharad Singh
