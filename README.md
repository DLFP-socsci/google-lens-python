# Google Lens Python

Google Lens Python is a Python package that allows you to reverse image search on Google Lens using Python, with the ability to search by file path or by URL.

## Installation

You can install Google Lens Python using pip:

```sh
pip install git+https://github.com/krishna2206/google-lens-python.git
```

## Usage

> **Note**: The language and location customization feature is currently experimental. The performance and accuracy of search results may vary depending on the selected host language (`hl`) and geolocation (`gl`) parameters. For the most reliable results, consider using the default settings.

To use Google Lens Python, import the `GoogleLens` class from the package and create an instance of it. You can optionally specify default language and location settings:

```python
from googlelens import GoogleLens

# Basic usage with default settings
lens = GoogleLens()

# With custom default language and location
lens = GoogleLens(default_language='en', default_location='us')
```

### Language and Location Settings

You can control the search language (`hl`) and geolocation (`gl`) in three ways:

1. Set defaults when creating the GoogleLens instance
2. Specify per-search settings
3. Use no settings to let Google determine them automatically

Examples of each approach:

```python
# 1. Set defaults at initialization
lens_fr = GoogleLens(default_language='fr', default_location='fr')

# 2. Specify per-search settings
lens = GoogleLens()
result = lens.search_by_file("image.jpg", language='de', location='de')

# 3. Use without any language/location settings
lens = GoogleLens()
result = lens.search_by_file("image.jpg")  # Google determines settings
```

### Searching by File

To search by a file path, use the `search_by_file` method:

```python
# Basic usage
search_result = lens.search_by_file("path/to/image.jpg")

# With specific language/location for this search only
search_result = lens.search_by_file(
    "path/to/image.jpg",
    language='es',  # Spanish
    location='mx'   # Mexico
)
```

### Searching by URL

To search by a URL, use the `search_by_url` method:

```python
# Basic usage
search_result = lens.search_by_url("https://example.com/image.jpg")

# With specific language/location for this search only
search_result = lens.search_by_url(
    "https://example.com/image.jpg",
    language='ja',  # Japanese
    location='jp'   # Japan
)
```

Both methods return a dictionary containing the search results.

### Common Language and Location Codes

Some commonly used codes:
- Languages (`language`): 'en' (English), 'es' (Spanish), 'fr' (French), 'de' (German), 'ja' (Japanese), 'ko' (Korean), 'zh' (Chinese)
- Locations (`location`): 'us' (United States), 'uk' (United Kingdom), 'fr' (France), 'de' (Germany), 'jp' (Japan), 'kr' (Korea), 'cn' (China)

If no language or location is specified, Google Lens will use its default behavior to determine these settings based on the request origin.

## Ideas

- Implement text detection (if possible)
- Implement translate feature (if possible)

## Contributing

Contributions to the Google Lens Python project are welcome! To contribute, please submit a pull request to the project's [GitHub repository](https://github.com/krishna2206/google-lens-python).

## License

MIT License

#### Notice

This license applies only to the files in this repository authored by Anhy Krishna Fitiavana (the "Author"). Other files may be subject to additional or different licenses.

#### License

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions: 

1. The above notice and this permission notice shall be included in all copies or substantial portions of the Software.

2. The Software is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. 

3. In no event shall the Author be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the Software or the use or other dealings in the Software.