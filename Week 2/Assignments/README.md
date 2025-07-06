# Summary of TF-IDF, CountVectorizer, and TfidfVectorizer Results

## Comparison of Word Scores

- **Manual TF-IDF** and **TfidfVectorizer** both produce floating-point scores that reflect the importance of each word in each document, considering both frequency and uniqueness.
- **CountVectorizer** produces integer counts, simply showing how many times each word appears in each document (Bag of Words).

| Method             | Output Type | Considers Word Rarity? | Example Score for 'the' |
|--------------------|-------------|------------------------|-------------------------|
| Manual TF-IDF      | Float       | Yes                    | 0.0 / 0.373 / 0.251     |
| CountVectorizer    | Integer     | No                     | 1                       |
| TfidfVectorizer    | Float       | Yes                    | 0.373 / 0.373 / 0.251   |

## Why Scores for Common Words Differ

- **Common words** like 'the' appear in every document.
- In **TF-IDF** (both manual and TfidfVectorizer), the IDF (inverse document frequency) for such words is low, because they are not unique or informative. This reduces their overall TF-IDF score.
- In **CountVectorizer**, only the raw count is considered, so common words can have high scores if they appear often, regardless of their informativeness.

**Conclusion:**  
TF-IDF methods downweight common words (like 'the') because they appear in all documents and thus are less useful for distinguishing between documents. CountVectorizer does not do this, so common words can dominate the representation.