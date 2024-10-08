# Custom Named Entity Recognition (NER) Model using spaCy for Resume Analysis

This project involves training a Named Entity Recognition (NER) model using [spaCy](https://spacy.io/), implemented in a Jupyter Notebook. The NER model can be customized to recognize specific entities based on the training data.

## Project Overview

The project demonstrates the following steps:
- Preprocessing of data for NER training.
- Training a custom NER model using spaCy.
- Test the model on evaluation data.
- Exporting and using the model in production.

## Prerequisites

- Python 3.10+
- Jupyter Notebook
- spaCy (version 3.7.2)
- Other dependencies: `numpy (version 1.25)`, `spacy-transformers`

To install the required dependencies, run:
```bash
pip install -r requirements.txt
```

## Data

The training data should follow the format used by spaCy, where each entity is labeled with a start position, end position, and entity type. Data can be loaded in JSON format, or as per your custom format.

## Notebook Instructions

1. **Load the Training Data**  
   Preprocess your dataset and prepare it in a format suitable for NER training.

2. **Train the Model**  
   - Initialize the spaCy pipeline for NER.
   - Add custom labels to the model.
   - Train the model iteratively using the provided training data.

3. **Evaluate the Model**  
   - Test the model on validation data.

4. **Save the Model**  
   Save the trained model for future use:
   ```python
   model.to_disk("model_output/")
   ```

## Usage

Once the model is trained and saved, you can load it and use it for NER tasks:

```python
import spacy
nlp = spacy.load("model_output/")
doc = nlp("Your input text here")
for ent in doc.ents:
    print(ent.text, '---->' , ent.label_)
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
