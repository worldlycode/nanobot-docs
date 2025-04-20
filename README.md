# NanoBot Documentation 🤖

This repository contains the documentation for the NanoBot POC project, built using MkDocs with the Material theme.

## 📚 Documentation Overview

Our documentation includes:
- Getting Started guide
- User Guide with detailed information about:
  - Document Processing
  - Vector Search
- API Reference
- Examples
- Blog posts

## 🛠️ Local Development

### Prerequisites
- Python 3.x
- pip (Python package installer)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/worldlycode/nanobot-docs
cd nanobot-docs
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows, use `.venv\Scripts\activate`
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

### Running the Documentation Server

To serve the documentation locally:
```bash
mkdocs serve
```

Visit `http://127.0.0.1:8000` to view the documentation.

### Building the Documentation

To build the static site:
```bash
mkdocs build
```

The built site will be in the `site` directory.

## 📖 Documentation Structure
```bash
docs/
├── index.md # Home page
├── getting-started.md # Getting started guide
├── user-guide/ # User guide section
│ ├── index.md
│ ├── document-processing.md
│ └── vector-search.md
├── api/ # API documentation
│ ├── database.md
│ └── services.md
├── examples.md # Usage examples
└── blog/ # Blog posts
└── index.md
```


## 🎨 Features

- 🌓 Dark/Light mode support
- 🔍 Full-text search
- 📱 Responsive design
- 🔗 Automatic navigation
- 💻 Code syntax highlighting
- 📊 Diagrams support (Mermaid)
- 📝 Google-style Python docstring support

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

[Add your license information here]

## 🔗 Links

- [Documentation Site](https://worldlycode.github.io/nanobot-docs)
- [Main Project Repository](https://github.com/srobertsphd/nanobot-poc)