# Semantic-Clustering-NLP
Unsupervised NLP project on Jane Austen’s novels to uncover semantic links between frequent content words. Trained Word2Vec embeddings and used hierarchical clustering with cosine and graph-based (Dijkstra) distances to compare contextual vs. structural similarity and explore their effect on word grouping.

## Project Overview
This project explores semantic relationships within literary texts by:
1. Comparing computational methods for defining "word similarity"
2. Analyzing vocabulary usage and meaning patterns in Jane Austen’s novels
3. Moving beyond simple co-occurrence to capture deeper contextual connections

## Dataset
The project uses a curated literary corpus by:
* Extracting text from three Jane Austen novels (*Emma*, *Persuasion*, *Sense and Sensibility*) sourced from **Project Gutenberg**
* Ensuring consistency in genre and writing style by selecting works from a single author
  
<img width="375" alt="Screenshot 2025-06-29 at 9 18 42 PM" src="https://github.com/user-attachments/assets/0b400474-6223-4c69-92c4-0226ecaae04f" />

### Sample Data

<img width="416" alt="Screenshot 2025-06-29 at 9 17 59 PM" src="https://github.com/user-attachments/assets/61845bbd-c009-42ef-a9bc-387d0c0e1629" />

## Requirements (Libraries)

```
nltk
spacy
gensim
sklearn
numpy
networkx
matplotlib
scipy
```

## Methodology 

### Preprocessing:
* Cleaned the raw text (lowercasing, punctuation removal, whitespace normalization, and elimination of chapter/title markers).
* Used spaCy for efficient tokenization, POS tagging, stopword removal, and lemmatization via a neural model.
  
### Word List Construction:
* Created a balanced list of 100 high-frequency content words (25 nouns, 25 verbs, 25 adjectives, 25 adverbs) using spaCy's POS tagging.
  
### Word Embedding & Similarity Calculation:
* Trained a Word2Vec Skip-gram model on the cleaned corpus to generate vector embeddings representing contextual meaning.
* Calculated cosine similarity between all word pairs, then transformed to a distance matrix for clustering.
  
### Clustering & Semantic Graph Construction:
* Applied hierarchical clustering using cosine distance to group closely related words.
* Constructed a graph-based semantic network by treating words as nodes and distances as weighted edges.
* Used Dijkstra’s algorithm (via NetworkX) to compute shortest semantic paths and explore indirect relationships.

## Results 

### Cosine-based Clustering:
The hierarchical clustering based on cosine distance revealed tightly bound word clusters reflecting immediate contextual similarity. Words with closely related emotional or functional meaning (e.g., hope, wish, feeling) consistently grouped together, highlighting surface-level associations captured directly by the Word2Vec embeddings.

<img width="1144" alt="Screenshot 2025-06-29 at 9 25 12 PM" src="https://github.com/user-attachments/assets/534a9853-7282-4d2e-b7a9-a99fab4a09b2" />

### Graph-based Clustering (Dijkstra's Algorithm):
Treating the cosine distance matrix as a weighted graph enabled the discovery of indirect, multi-step semantic relationships. Using Dijkstra’s algorithm to compute shortest semantic paths uncovered broader thematic links—for example, character names like Anne and Emma appeared in proximity to abstract concepts such as love and belief, indicating deeper narrative connections beyond direct co-occurrence.

<img width="1134" alt="Screenshot 2025-06-29 at 9 26 23 PM" src="https://github.com/user-attachments/assets/6cc161e5-ed82-428e-ad63-e418c9f678f4" />

## Conclusion/ Key Insights
While cosine-based clustering provided high-resolution groupings of similar vocabulary, the graph-based approach offered a more expansive semantic perspective. The divergence in clustering outcomes emphasized how the choice of distance metric significantly influences linguistic interpretations in literary corpora.

## How to Cite

If you use this work in your research, please cite:
```
@software{sharan2025semanticclustering,
  author = {Sharan, Tanya},
  title = {Semantic Clustering of Literary Vocabulary Using Word2Vec and Graph-Based Distance Measures},
  year = {2025},
  url = {https://github.com/yourusername/Semantic-Clustering-using-NLP}
}
```










