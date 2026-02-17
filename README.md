# German Language Learning Dataset

A community-maintained German-English learning dataset with vocabulary, grammar rules, and example sentences organized by CEFR proficiency levels (A1-C1).

## Project Status

> **Active Development** - This project is currently under active development. Data and features may change without prior notice.

We welcome contributions from educators, linguists, developers, and German language enthusiasts. Your help in improving accuracy, adding new content, and reporting errors is greatly appreciated.

## Overview

This dataset is designed to help developers build language learning applications, researchers study German linguistics, and educators create learning materials.

| Category | Count | Description |
|----------|-------|-------------|
| Alphabet | 43 entries | German alphabet with IPA pronunciation |
| Vocabulary | 8,242 words | Organized by CEFR level (A1-C1) |
| Grammar | 365 rules | Across 31 grammatical categories |
| Sentences | 2,300 examples | Tagged with CEFR levels |

## Dataset Structure

```
data/
  alphabet.jsonl          # German alphabet with pronunciation
  grammar.jsonl           # Grammar rules and explanations
  sentences.jsonl         # Example sentences with translations
  vocabulary/
    a1.jsonl              # Beginner (834 words)
    a2.jsonl              # Elementary (1,408 words)
    b1.jsonl              # Intermediate (2,000 words)
    b2.jsonl              # Upper-Intermediate (2,000 words)
    c1.jsonl              # Advanced (2,000 words)
```

## Data Format

All files use JSON Lines format (one JSON object per line).

### Vocabulary Entry

```json
{
  "german": "Haus",
  "english": "house",
  "gender": "das",
  "pos": "noun",
  "example_de": "Das Haus ist groß.",
  "example_en": "The house is big."
}
```

### Grammar Entry

```json
{
  "rule_id": "noun_001",
  "category": "nouns",
  "rule": "All German nouns are capitalized",
  "explanation": "Unlike English, German capitalizes all nouns, not just proper nouns.",
  "examples": ["der Hund (the dog)", "das Buch (the book)"]
}
```

### Sentence Entry

```json
{
  "sentence_de": "Ich lerne Deutsch.",
  "sentence_en": "I am learning German.",
  "cefr_level": "A1",
  "word_count": 3,
  "grammar_features": ["personal_pronoun", "present_tense"]
}
```

## CEFR Levels

| Level | Name | Description |
|-------|------|-------------|
| A1 | Beginner | Basic phrases, everyday expressions |
| A2 | Elementary | Routine tasks, simple direct exchange |
| B1 | Intermediate | Main points on familiar matters |
| B2 | Upper-Intermediate | Complex texts, technical discussions |
| C1 | Advanced | Demanding texts, implicit meaning |

## Usage

### Python

```python
import json

# Load A1 vocabulary
with open('data/vocabulary/a1.jsonl', 'r', encoding='utf-8') as f:
    a1_vocab = [json.loads(line) for line in f]

print(f"Loaded {len(a1_vocab)} A1 words")

# Search for a word
for word in a1_vocab:
    if word['german'] == 'Haus':
        print(word)
```

### JavaScript

```javascript
const fs = require('fs');

const data = fs.readFileSync('data/vocabulary/a1.jsonl', 'utf-8');
const vocab = data.trim().split('\n').map(line => JSON.parse(line));

console.log(`Loaded ${vocab.length} words`);
```

## Data Sources and Attribution

This dataset was compiled from the following open sources:

| Source | Data Type | License |
|--------|-----------|---------|
| [Wiktionary](https://en.wiktionary.org/) | Vocabulary | CC BY-SA 4.0 |
| [Tatoeba](https://tatoeba.org/) | Sentences | CC BY 2.0 FR |

We acknowledge and thank the contributors to both Wiktionary and Tatoeba for making their work freely available.

## License

This dataset is released under mixed licenses reflecting the source data:

- **Vocabulary data**: [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) (from Wiktionary)
- **Sentence data**: [CC BY 2.0 FR](https://creativecommons.org/licenses/by/2.0/fr/) (from Tatoeba)

See the `LICENSES/` folder for full license texts.

### What This Means

You are free to:
- Use this data in your applications (including commercial)
- Modify and build upon the data
- Distribute copies of the data

Requirements:
- Credit the original sources (Wiktionary, Tatoeba)
- Indicate if you made changes
- Share vocabulary derivatives under CC BY-SA 4.0

## Contributing

We welcome contributions from the community. You can help by:

- Adding new vocabulary entries
- Correcting translation errors
- Improving example sentences
- Reporting data quality issues

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting a pull request.

## API

This dataset powers the German Language API, a free REST API for German language learning:

- Documentation: [https://rep12.com](https://rep12.com)
- API Base URL: `https://german-language.onrender.com`

## Related Projects

- [German Language API Documentation](https://github.com/IamHamud/German-Language-API) - API docs website

## Contact

For questions, issues, or suggestions, please open an issue on this repository.

Maintainer: [@IamHamud](https://github.com/IamHamud) | [LinkedIn](https://www.linkedin.com/in/iamhamud/)

## Disclaimer

**No Warranty**: This dataset is provided "as is" without warranty of any kind, express or implied. The maintainers make no guarantees regarding accuracy, completeness, or fitness for any particular purpose.

**Limitation of Liability**: In no event shall the maintainers be liable for any damages arising from the use of this data.

**User Responsibility**: Users are responsible for verifying data accuracy for their specific use cases. This resource is intended for educational purposes and should not be the sole reference for critical applications.

**Third-Party Use**: We are not responsible for how third parties use, modify, or redistribute this data. Any misuse of this dataset is solely the responsibility of those parties.
