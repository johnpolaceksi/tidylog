# tidylog

Opinionated log housekeeping tool with dry-run support

Small but I use it weekly.

## Installation

```bash
pip install -r requirements.txt
python -m logwash --help
```

## Usage

```bash
# show what would be cleaned, change nothing
logwash ./logs --older-than 30 --dry-run

# archive logs older than 30 days
logwash ./logs --older-than 30 --archive ./backup
```

## Features

- Scan directories for log files by glob pattern
- Archive matched logs into a timestamped .tar.gz
- Exit codes friendly for cron and CI
- Filter by age (--older-than) or size (--larger-than)
- Dry-run mode shows what would happen, touches nothing

## Project structure

```text
├── docs/
│   ├── configuration.md
│   ├── faq.md
│   ├── roadmap.md
│   └── usage.md
├── examples/
│   └── quickstart.md
├── logwash/
│   ├── __init__.py
│   ├── __main__.py
│   ├── cli.py
│   └── utils.py
├── tests/
│   └── test_cli.py
├── .gitattributes
├── .gitignore
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── Makefile
├── pyproject.toml
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
