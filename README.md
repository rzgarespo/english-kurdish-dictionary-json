# English-Kurdish Translator JSON

## Overview

The English-Kurdish Translator project provides a collection of JSON files containing translations for English words to Kurdish. The translations are organized alphabetically, making it convenient for developers to use and integrate into their applications.

## Features

- **Translation Files:** JSON files are organized alphabetically, each containing translations for a specific range of English words.
- **JSON Structure:** Translations are structured with each English word having a corresponding entry with Kurdish translations.
- **Scalability:** The project can be extended, and new translations can easily be added.

## Usage

1. **Download JSON Files:**
   - Navigate to the [main]([https://github.com/rzgarespo/english-kurdish-dictionary-json/)  repository page.
   - Download the desired JSON file(s) containing translations.

2. **Integrate into Your Project:**
   - Include the downloaded JSON file(s) in your project.
   - Access translations programmatically based on the structure provided in the JSON files.

3. **Example Usage in Python:**
 ```python
import requests
import json
import re

def get_translation(word):
    try:
        url_char = word[0].capitalize()
        wc = word.capitalize()
        url = f"https://raw.githubusercontent.com/rzgarespo/english-kurdish-dictionary-json/main/{url_char}_translations.json"
        res = requests.get(url)

        if res.status_code == 200:
            data = res.json()
   
            if wc in data and 'kurdish' in data[wc]:
                print(f"{word}: {data[wc]['kurdish']}")
            else:
                print(f"{wc} is not found")
        else:
            print("Failed to fetch data")

    except Exception as e:
        print(f"An error occurred: {e}")

myinput = input("write a few words").strip()
filtered_input = re.sub(r'[^a-zA-Z\s]', '', myinput)
mylist =filtered_input.split()
for x in mylist:
    get_translation(x)
    
 ```
   4. **Example Usage in JavaScript:**
   ```javascript
       <script>
        async function getTranslate(word) {
            const url = 'https://raw.githubusercontent.com/rzgarespo/english-kurdish-dictionary-json/main/W_translations.json';

            try {
                // Fetch JSON data
                const response = await fetch(url);

                // Check if the request was successful
                if (!response.ok) {
                    throw new Error(`HTTP error! Status: ${response.status}`);
                }

                // Parse JSON
                const translations = await response.json();

                // Access translations for the provided word
                const kurdishTranslations = translations[word]?.kurdish || [];
                document.getElementById('demo').innerHTML = word +": "+ kurdishTranslations;
            } catch (error) {
                console.error('Error fetching data:', error.message);
            }
        }

        // Example usage
        getTranslate('Wadding');
    </script>
   ```

## Contributing

Contributions are welcome! Feel free to open issues or submit pull requests to enhance the project.

## License

This project is licensed under the [GNU GENERAL PUBLIC LICENSE](LICENSE).


