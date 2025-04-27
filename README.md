# NanoBot-Dev Documentation 🤖

This repository contains the documentation for the NanoBot-Dev project, built using [MkDocs](https://www.mkdocs.org/) with the [Material theme](https://squidfunk.github.io/mkdocs-material/).

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
The packages this will install are as follows
```txt
mkdocs-material
mkdocstrings[python]
pymdown-extensions
ghp-import
```

### Running the Documentation Server

To serve the documentation locally:
```bash
mkdocs serve
```

Visit `http://127.0.0.1:8000` to view the documentation.

## Deploying to GitHub

To deploy live on Github Pages site:
```bash
mkdocs gh-deploy
```

The site will update and be live on [WorldlyCode GitHub Pages](https://worldlycode.github.io/nanobot-dev-docs/)

## 📖 Documentation Structure

```bash
docs/
├── index.md            # Home page
├── getting-started.md  # Getting started guide
├── examples.md         # Usage examples
├── user-guide/         # User guide section
│ ├── index.md
│ ├── doc_1.md
│ └── doc_2.md
│ └── ...
├── api/                # API documentation
│ ├── database.md
│ └── services.md
│ └── ...
└── blog/               # Blog posts
│ ├── index.md
│ └── blog_post_1
│ └── blog_post_2
│ └── ...
├── assets/             # files for inclusion in posts
│ ├── images
│ └── pdfs
```

The key file that is used to structure the appearance of these files is in the `mkdocs.yml` file in the root directory.  Every addition of a file must be updated in this file.  

## 🎨 Features

- 🌓 Dark/Light mode support
- 🔍 Full-text search
- 📱 Responsive design
- 🔗 Automatic navigation
- 💻 Code syntax highlighting
- 📊 Diagrams support (Mermaid)
- 📝 Google-style Python docstring support

## 🤝 Contributing

At this time, contributions to documentation are limited to invited collaborators only

## 🔗 Links

- [Documentation Site](https://worldlycode.github.io/nanobot-dev-docs)
- [Main Project Repository](https://github.com/worldlycode/nanobot-dev)

**Note:** Though the documentation and resources discussed are open to all, the project repo is currently private while we are under development. mkdocs