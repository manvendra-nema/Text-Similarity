# 🔍 Task: Text Similarity (45 Marks) ✨

## 📝 Task Definition
Given two sentences, calculate the similarity between them. The similarity is given as a score ranging from 0 to 5.

### 📊 Train Datapoint Examples
| Score | Sentence 1                          | Sentence 2                          |
|-------|--------------------------------------|-------------------------------------|
| 4.750 | A young child is riding a horse.     | A child is riding a horse.          |
| 2.400 | A woman is playing the guitar.       | A man is playing guitar.            |

The dataset is already divided into training and validation sets in the files - `train.csv` and `dev.csv`, respectively. Both files are provided in the zip file attached to the assignment. Note that the files are tab-separated. A testing file excluding the score field will be provided during the demo for inference.

Create dataset classes and data loaders appropriately for your training and evaluation setups.

## 🛠️ Setups

### Setup 1A: BERT Model 🧠
- Train a BERT model (`google-bert/bert-base-uncased` · Hugging Face) using HuggingFace for the task of Text Similarity.
- Obtain BERT embeddings using a special token for separating multiple sentences and an appropriate linear layer or `BertForSequenceClassification` for a float output.
- Choose a suitable loss function.
- Report the required evaluation metric on the validation set.
- **Marks:** 10

### Setup 1B: Sentence-BERT Model 🔗
- Use the Sentence-BERT model ([paper](https://arxiv.org/pdf/1908.10084.pdf)) and the SentenceTransformers framework.
- Encode the sentences and determine the cosine similarity between these embeddings for the validation set.
- Report the required evaluation metric on the validation set.


### Setup 1C: Fine-Tuned Sentence-BERT Model 🚀
- Fine-tune the Sentence-BERT model for the task of STS using the `CosineSimilarityLoss` function.
- Report the required evaluation metric on the validation set (reference: Semantic Textual Similarity — Sentence-Transformers documentation).
- Train for at least two epochs and surpass the performance of Setup 1B.
- Save and submit model checkpoints.


### Note
For setups 1B and 1C, the data has a score out of 5. However, cosine similarity returns a value between 0 and 1. Appropriately scale the cosine similarity to the score column's scale before evaluation. You may also need to scale down the score to a scale of 1 for training the sentence transformers.

## 📊 Evaluation Metrics
- Pearson Correlation

## 📝 Report 
1. Generate the following plots for Setup 1A and 1C:
   - Loss Plot: Training Loss and Validation Loss vs. Epochs
2. Analyze and explain the obtained plots.
3. Provide a brief comparison and explanation for the performance differences between the three setups.
4. Provide all evaluation metrics for all setups in your report pdf.
