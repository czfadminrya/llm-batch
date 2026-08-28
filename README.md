# llm-batch

Feed a thousand prompts, get a thousand answers

## Usage

```bash
python batch.py prompts.jsonl -o answers.jsonl --workers 4
```

## Install

```bash
pip install -r requirements.txt
export OPENAI_API_KEY=sk-...
```

## Features

- Idempotent: skips ids already present in the output
- Concurrent workers with a rate ceiling
- JSONL in, JSONL out: stream-safe for huge inputs
- Retries failed items with backoff, logs them aside

## Project structure

```text
├── .github/
│   └── dependabot.yml
├── docs/
│   ├── configuration.md
│   ├── development.md
│   ├── roadmap.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── tests/
│   └── test_smoke.py
├── .gitignore
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── LICENSE
├── Makefile
├── batch.py
├── prompts.sample.jsonl
└── requirements.txt
```

## Development

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
python -m pytest -q
```

## License

MIT. Do whatever you want.
