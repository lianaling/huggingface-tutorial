# HuggingFace Transformers Tutorial

Following this [course](https://huggingface.co/course/chapter0?fw=pt) and learning how to use and fine-tune transformer models

##Setup

- Download Jupyter Notebook extension for VSCode
- Download Python

## About Local Models

Before running the code (or anything similar) below

```py
checkpoint = "distilbert-base-uncased-finetuned-sst-2-english"
tokenizer = AutoTokenizer.from_pretrained("tokenizers/" + checkpoint, local_files_only=True)
model = AutoModelForSequenceClassification.from_pretrained("models/" + checkpoint, local_files_only=True)
```

Load and save any tokenizer/model from HuggingFace first

```py
checkpoint = "distilbert-base-uncased-finetuned-sst-2-english"

# Load model
tokenizer = AutoTokenizer.from_pretrained(checkpoint)
model = AutoModelForSequenceClassification.from_pretrained(checkpoint)

# Save model into local directory
tokenizer.save_pretrained("tokenizers/" + checkpoint)
model.save_pretrained("models/" + checkpoint)
```

This is because the models/tokenizers can be too large to be pushed onto GitHub