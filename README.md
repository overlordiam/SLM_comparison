# SLM_comparison

## Introduction
This notebook compares four different Small Language Models (Mistral-7B, Zephyr_7B, Orca-7B, and Phi-2, which is a 3B model) in a question-answering task. 
The ground truth answers are obtained by passing the same questions to Gemini-pro, a trusted Large Language Model. At the end of the notebook, we have graphs displaying 
the performance of each SLM against six commonly used metrics: Exact match, F1-Score, BLEU score, ROUGE score, BERT-based similarity score, and Sentence-transformer-based 
similarity score.

## Technologies and Concepts
- Python
- Langchain
- VectorDB (ChromaDB)
- Plotly
- Retrievel Augmented Generation (RAG)
- Small and Large Language Models
- Object Oriented Programming

## Visualization
Some comparisons and analyses done here:

![image](https://github.com/user-attachments/assets/24d56424-7b91-4ed6-852f-332aa8200a60)

<br>

![image](https://github.com/user-attachments/assets/7843662e-5e52-440e-a66e-b4c7d7e8dca6)

<br>

![image](https://github.com/user-attachments/assets/67442263-431b-4ecc-8d04-e41487d16a6a)

<br>

## Observations

- **BLEU, ROUGE-1, ROUGE-2, ROUGE-L, Exact match, and F1 scores are expectedly low**: Since the answers generated by the models are not just simple sentences, quantifying their performance only by overlaps, precision, and recall will not be sufficient.

### Exact Match Scores
- The scores are zero for all the models on all the sentences. 

### F1 Scores
- **Zephyr**: Higher and more consistent F1 scores across evaluations. F1 score balances precision and recall, and Zephyr's higher scores indicate it effectively retrieves relevant information with fewer false positives.
- **Mistral**: Lower F1 scores compared to Zephyr, indicating less effective retrieval of relevant information.
- **Orca**: Some higher scores, but generally lower than Zephyr, suggesting it is less consistent.
- **Phi-2**: Scores vary significantly and are generally lower than Zephyr, indicating less effective performance.

### BLEU Scores
- **Zephyr**: Generally higher BLEU scores, which measure the accuracy of generated text compared to reference text. Higher scores indicate better performance in language generation tasks.
- **Mistral**: Very low BLEU scores, suggesting poor performance in generating accurate text.
- **Orca**: Similar to Mistral, with generally low scores.
- **Phi-2**: Low and inconsistent BLEU scores, indicating poor performance in text generation.

### ROUGE Scores
- **Zephyr**: Higher ROUGE scores, which measure the overlap between the model-generated text and reference text in terms of recall, precision, and F1. Higher ROUGE scores suggest better performance in generating text that closely matches the reference.
- **Mistral**: Lower ROUGE scores compared to Zephyr, indicating less effective text generation.
- **Orca**: Some high scores, but less consistent compared to Zephyr.
- **Phi-2**: Generally lower and more inconsistent scores.

### BERT Cosine Similarity
- **Zephyr**: Shows consistently high similarity scores across various evaluations, indicating that Zephyr’s outputs are more semantically similar to the reference texts. This means that Zephyr effectively captures the meaning of the input and produces relevant and contextually appropriate responses.
- **Mistral**: The scores are lower and less consistent compared to Zephyr. This suggests that Mistral’s outputs are less semantically aligned with the reference texts, leading to less relevant responses.
- **Orca**: Similar to Mistral, the scores are generally lower and show greater variability, indicating inconsistent performance in capturing semantic similarity.
- **Phi-2**: Scores are also lower and less consistent, reflecting less effective performance in generating semantically similar text compared to Zephyr.

### Sentence Transformer Cosine Similarity
- **Zephyr**: Again, Zephyr demonstrates higher and more consistent similarity scores. Sentence Transformers are powerful tools for measuring the similarity between sentences, and Zephyr’s high scores indicate its ability to generate responses that are closely aligned with the meaning of the reference texts.
- **Mistral**: Lower scores suggest that Mistral struggles to maintain semantic similarity with the reference texts, leading to less relevant outputs.
- **Orca**: While some scores might be competitive, they are generally lower and more variable than Zephyr’s, indicating less reliability in generating semantically similar responses.
- **Phi-2**: Similar to the other models, Phi-2 shows lower and less consistent scores, reflecting poorer performance in maintaining semantic similarity.

**These high scores demonstrate Zephyr’s robustness in generating semantically relevant and meaningful responses, outperforming Mistral, Orca, and Phi-2 in most evaluations.**

- **It is important to note that all the models are very close in scores**: Some models outperform others in certain evaluations.
- **The overall scores are low because of heavy quantization**: The models are 4-bit quantized to fit space constraints. If we were to test the full models, the performance increase would be significant.
- **This notebook is to experiment and draw comparisons between the models**: Even though the scores are low, relatively we can understand the standings in models' performances.

