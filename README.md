#  Negation Handling

Extract **symptoms, diseases, and body parts** from clinical notes with special attention to **negations** (e.g., "no", "denies", "without"), which are critical in medical text interpretation.

## Features
- Named Entity Recognition (NER) with **scispaCy** (`en_ner_bc5cdr_md`)
- Detect symptoms, diseases, and body parts
- **Negation detection**: distinguishes “pain” vs. “no pain”
- Dictionary-based fallback for domain-specific terms

## Special Tools Used
- **SpaCy** – tokenization, NER
- **scispaCy** – biomedical NER models
- **Python standard libs** – simple data handling

## Learning Path
1. Learn basic NLP: tokenization, lemmatization
2. Understand named entity recognition (NER)
3. Implement **negation detection** in clinical text
4. Add domain-specific dictionaries for robustness
5. Combine NER + dictionary + negation for reliable extraction

## Quick Usage

```python
texts = [
    "Patient reports tooth pain but denies swelling.",
    "No evidence of dental caries, patient complains of sensitivity."
]

for t in texts:
    info = extract_medical_info(t)
    print(info)

# Example output:
# {
#   "text": "Patient reports tooth pain but denies swelling.",
#   "symptoms": [{"name": "tooth pain", "negated": False}],
#   "diseases": [],
#   "body_parts": ["tooth"]
# }
