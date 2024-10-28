# Claude API Quickstart

This repository contains a quick start guide for setting up and using the Anthropic Claude API with Python.

## Prerequisites

- Python 3.7 or higher
- pip (Python package installer)
- An Anthropic API key ([Get one here](https://console.anthropic.com/))

## Installation

1. Clone this repository:
```bash
git clone https://github.com/antymijaljevic/claude-quickstart.git
cd claude-quickstart
```

2. Create a virtual environment:
```bash
python3 -m venv claude-env
```

3. Activate the virtual environment:

On Unix or MacOS:
```bash
source claude-env/bin/activate
```

4. Install the required packages:
```bash
pip3 install anthropic
```

5. Set up your API key:

On Unix or MacOS:
```bash
export ANTHROPIC_API_KEY='your-api-key-here'
```

## Usage

1. Make sure your virtual environment is activated
2. Run the quickstart script:
```bash
python3 claude_quickstart.py
```

## Project Structure

```
claude-quickstart/
├── README.md
├── claude_quickstart.py
├── requirements.txt
└── claude-env/
```