# Hindi NLP Text Processing

## Project Overview

This project performs three Natural Language Processing tasks on Hindi text:

1. **Punctuation Restoration:** Adds punctuation marks to Hindi text that originally has no punctuation.
2. **Sentence Ordering:** Attempts to arrange jumbled sentences in a meaningful order using semantic similarity.
3. **Hindi-to-English Translation:** Groups five consecutive ordered sentences and translates each group into English.

## Models Used

| Task | Pretrained Model |
|---|---|
| Punctuation Restoration | Horizon-Labs/punctuation-restoration-small |
| Sentence Ordering | sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2 |
| Translation | Helsinki-NLP/opus-mt-hi-en |

All three models are pretrained. No model training or fine-tuning was performed.

## Technologies Used

- Python
- Google Colab
- PyTorch
- Hugging Face Transformers
- Sentence Transformers
- Scikit-learn

## Workflow

1. Load the Hindi text dataset.
2. Restore punctuation in all input files.
3. Extract individual sentences.
4. Generate sentence embeddings and reorder sentences using cosine similarity.
5. Divide ordered sentences into groups of five.
6. Translate each group into English.
7. Save the generated outputs as text files.

## Dataset

The project uses seven Hindi text files containing text without punctuation.

## Output

For each input file, the project generates:
- Punctuated Hindi text.
- Reordered Hindi sentences.
- Translated English text.

## Limitations

- Punctuation restoration may not always be perfect.
- Sentence ordering uses a greedy semantic-similarity approach and cannot guarantee the original sentence order.
- Translation quality depends on the pretrained model.
- The last group may contain fewer than five sentences.

## Execution

The project was implemented in Google Colab using GPU acceleration.

Install dependencies:

```bash
pip install transformers sentence-transformers sentencepiece accelerate sacremoses scikit-learn
```

Upload the dataset ZIP file to Google Colab, extract it, and run the notebook cells in sequence.

## Repository Contents

- `NLP_Project.ipynb` – Complete implementation of the project.
- `README.md` – Project description, workflow, models, and instructions.

## Pretrained Model Sources

- [Punctuation Restoration](https://huggingface.co/Horizon-Labs/punctuation-restoration-small)
- [Sentence Ordering](https://huggingface.co/sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2)
- [Translation](https://huggingface.co/Helsinki-NLP/opus-mt-hi-en)

## Project Results

- 7 Hindi input files processed.
- 7 punctuated output files generated.
- 7 reordered output files generated.
- 77 translated groups generated.
