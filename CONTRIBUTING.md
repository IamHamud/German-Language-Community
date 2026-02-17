# Contributing to German Language Community Dataset

Thank you for your interest in contributing. This document provides guidelines for submitting contributions.

## How to Contribute

### Reporting Issues

If you find errors in the data (incorrect translations, typos, wrong grammar explanations), please open an issue with:

1. The file containing the error
2. The specific entry (include the German word or sentence)
3. What is wrong
4. The correct information (if known)

### Submitting Changes

1. Fork this repository
2. Create a branch for your changes (`git checkout -b add-new-words`)
3. Make your changes following the data format guidelines below
4. Test your changes (ensure valid JSON)
5. Commit with a clear message describing what you added/changed
6. Open a pull request

## Data Format Guidelines

### Vocabulary Entries

Each vocabulary entry must include:

| Field | Required | Type | Description |
|-------|----------|------|-------------|
| `german` | Yes | string | German word |
| `english` | Yes | string | English translation |
| `gender` | For nouns | string | `der`, `die`, or `das` |
| `pos` | Yes | string | Part of speech (see below) |
| `example_de` | Recommended | string | Example sentence in German |
| `example_en` | Recommended | string | Example sentence in English |

Valid parts of speech (`pos`):
- `noun`
- `verb`
- `adjective`
- `adverb`
- `preposition`
- `conjunction`
- `pronoun`
- `interjection`
- `article`

Example of a valid entry:

```json
{"german": "Baum", "english": "tree", "gender": "der", "pos": "noun", "example_de": "Der Baum ist hoch.", "example_en": "The tree is tall."}
```

### Grammar Rules

Each grammar rule must include:

| Field | Required | Type | Description |
|-------|----------|------|-------------|
| `rule_id` | Yes | string | Unique identifier (category_number) |
| `category` | Yes | string | Grammar category |
| `rule` | Yes | string | Short rule statement |
| `explanation` | Yes | string | Detailed explanation |
| `examples` | Yes | array | List of example strings |

### Sentences

Each sentence must include:

| Field | Required | Type | Description |
|-------|----------|------|-------------|
| `sentence_de` | Yes | string | German sentence |
| `sentence_en` | Yes | string | English translation |
| `cefr_level` | Yes | string | A1, A2, B1, B2, or C1 |
| `word_count` | Yes | integer | Number of words in German sentence |
| `grammar_features` | Recommended | array | Grammar concepts demonstrated |

## JSON Validation

Before submitting, validate that each line is valid JSON:

```python
import json

with open('your_file.jsonl', 'r') as f:
    for i, line in enumerate(f, 1):
        try:
            json.loads(line)
        except json.JSONDecodeError as e:
            print(f"Line {i}: {e}")
```

## CEFR Level Guidelines

When assigning CEFR levels:

| Level | Vocabulary Characteristics |
|-------|---------------------------|
| A1 | Basic everyday words (numbers, colors, family, food) |
| A2 | Common verbs, simple adjectives, routine vocabulary |
| B1 | Work, travel, opinions, more abstract concepts |
| B2 | Technical terms, idiomatic expressions, nuanced vocabulary |
| C1 | Academic, professional, rare, and specialized terms |

## What We Accept

- New vocabulary entries with accurate translations
- Corrections to existing entries
- Additional example sentences
- Grammar rule improvements
- Better IPA pronunciations

## What We Do Not Accept

- Machine-translated content without human verification
- Copyrighted content from commercial dictionaries
- Offensive or inappropriate content
- Duplicate entries

## Code of Conduct

- Be respectful in all interactions
- Provide constructive feedback
- Focus on improving the dataset quality
- Credit sources when applicable

## Review Process

All pull requests are reviewed before merging. We check for:

1. Valid JSON format
2. Accurate translations
3. Appropriate CEFR level assignment
4. Compliance with data format

Reviews typically take 3-7 days. We may request changes before merging.

## Questions

If you have questions about contributing, open an issue with the "question" label.
