# English-Kurdish Translator JSON

## Overview

The English-Kurdish Translator project provides a collection of JSON files containing translations for English words to Kurdish. The translations are organized alphabetically, making it convenient for developers to use and integrate into their applications.

## Features

- **Translation Files:** JSON files are organized alphabetically, each containing translations for a specific range of English words.
- **JSON Structure:** Translations are structured with each English word having a corresponding entry with Kurdish translations.
- **Scalability:** The project can be extended, and new translations can easily be added.

## Usage

1. **Download JSON Files:**
   - Navigate to the [main]([https://github.com/rzgarespo/english-kurdish-dictionary-json/))  repository page.
   - Download the desired JSON file(s) containing translations.

2. **Integrate into Your Project:**
   - Include the downloaded JSON file(s) in your project.
   - Access translations programmatically based on the structure provided in the JSON files.

3. **Example Usage in Python:**
   ```python
   import json

   # Load JSON file
   with open('W_translations.json', 'r', encoding='utf-8') as json_file:
       translations = json.load(json_file)

   # Access translations for a specific word
   word = "Wadding"
   kurdish_translations = translations.get(word, {}).get("kurdish", [])
   print(f"{word}: {kurdish_translations}")
   ```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to enhance the project.

## License

This project is licensed under the [GNU GENERAL PUBLIC LICENSE](LICENSE).


