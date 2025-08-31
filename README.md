# Translator

A Python-based language translation tool that leverages OpenAI models via the GitHub AI endpoint. It is designed to translate text between languages and can be run locally or integrated into GitHub workflows for automated translation of issue comments.

## Features
- Translates text from one language to another using OpenAI's GPT models.
- Configurable source and target languages via environment variables.
- Integrates with GitHub Actions to automate translation of issue comments.
- Secure authentication using GitHub tokens.

## Usage

### Local Usage
1. Install dependencies:
	```bash
	pip install -r requirements.txt
	```
2. Set environment variables:
	- `GH_TOKEN`: Your GitHub token (required)
	- `source_language`: Source language (default: English)
	- `target_language`: Target language (default: French)
3. Run the script:
	```bash
	python main.py "Text to translate"
	```

### GitHub Actions Integration
- The workflow in `.github/workflows/translate.yaml` automates translation for issue comments and manual dispatches.
- When an issue comment is created on an issue titled `Translation: <source_language> to <target_language>`, the workflow triggers translation and updates the comment with the result.

## Configuration
- Edit `.github/ISSUE_TEMPLATE/translation.md` to customize the translation issue template.
- Modify `main.py` to change model or endpoint settings if needed.

## Example
```bash
python main.py "Hello, how are you?"
```

## License
MIT
