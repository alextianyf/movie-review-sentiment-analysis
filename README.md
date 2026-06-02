# Movie Review Sentiment Analysis

Teach a computer to read an IMDB movie review and decide whether the critic
**liked** the film (positive) or **hated** it (negative).

This is a beginner-friendly machine-learning project: it turns review text into
numbers with **TF-IDF**, trains a **Logistic Regression** classifier, and reaches
about **90% accuracy** on reviews it has never seen - while staying simple enough
to explain every step.

---

## What's in here

| File | What it is |
|------|------------|
| **`sentiment-analysis-teaching.ipynb`** | Full tutorial. Every step explained with analogies and presentation notes. Use this to **learn** and to prepare slides. |
| **`sentiment-analysis-submission.ipynb`** | Clean, well-commented version - the **deliverable to hand in**. |
| `data/IMDB Dataset.csv` | 50,000 labelled reviews (25k positive / 25k negative). |
| `requirements.txt` / `environment.yml` | The exact libraries needed, for reproducibility. |

Both notebooks run the same analysis and produce the same result - they differ
only in how much they explain.

---

## How to run it

The project uses a conda environment named **`movie-review-sentiment-analysis`**.

**1. Create the environment** (first time only):

```powershell
conda env create -f environment.yml
```

**2. Activate it:**

```powershell
conda activate movie-review-sentiment-analysis
```

**3. Open a notebook:**

```powershell
jupyter notebook sentiment-analysis-teaching.ipynb
```

Then in Jupyter, choose the kernel **"Python (movie-review-sentiment-analysis)"**
and run the cells top to bottom (`Shift + Enter`).

If `conda` isn't recognised on this machine, initialise it once with the full
path: `& "C:\Users\alext\miniconda3\Scripts\conda.exe" init powershell`, then
restart the terminal.

---

## The 8 steps (the story the project tells)

1. **Look at the data** - 50k reviews, balanced 50/50, peek at examples.
2. **Clean the text** - strip HTML tags (`<br />`) and remove duplicates.
3. **Turn words into numbers** - TF-IDF scores each word by how distinctive it is.
4. **Split** - 80% to study, 20% kept hidden for a fair final exam.
5. **Train** - Logistic Regression learns a score (weight) for every word.
6. **Grade** - about 90% accuracy, plus a confusion matrix of its mistakes.
7. **Peek inside its brain** - list the words it found most positive/negative.
8. **Try it live** - type any review and get a prediction with a confidence score.

---

## The interesting finding

The mission noted that words like *"dark"* or *"heavy"* can be **compliments** in
film criticism. The model learned this on its own: `dark`, `brutal`, and `twisted`
all came out slightly **positive**, while `boring`, `slow`, and `predictable` were
strongly negative. Its hardest cases are sarcasm and context-dependent words - a
good discussion point about why language is hard for computers.

---

Built as a teaching project. Model: TF-IDF + Logistic Regression (scikit-learn).
