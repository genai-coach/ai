# Setup Guide

## Prerequisites
- Python 3.9+
- Git with LFS support
- Text editor (VS Code recommended)

## Installation Steps

1. **Clone Repository**
```bash
git clone https://github.com/genai-coach/ai.git
cd ai
git lfs install
git lfs pull
```

2. **Set Up Python Environment**
```bash
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

3. **Verify Installation**
```bash
python -c "import openai, langchain; print('Setup complete!')"
```

## Troubleshooting
- **Git LFS Issues**: Ensure Git LFS is installed: `git lfs version`
- **Python Issues**: Use Python 3.9+ for best compatibility
- **Import Errors**: Try `pip install --upgrade -r requirements.txt`
