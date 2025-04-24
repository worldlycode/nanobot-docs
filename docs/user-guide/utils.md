# Utils (Utility function) Folder

April 24, 2025

In `app/utils` directory there are several modules which handle some housekeeping tasks.  We describe these below

## `tree.py`

The `tree.py` utility draws a tree of the project or directory.  To run this from the **root directory** command line (from the `nanobot-poc` directory), entering

```bash
python -m app.utils.tree/utils
```

will print the following structure in the terminal
```bash
app/
├── utils/
│   ├── __init.__.py
│   ├── json_formatter.py
│   ├── logger.py
│   ├── logging_examples.py
│   ├── tree.py
│   ├── file_handling.py
│   ├── tokenizer.py
```

This runs it using the Python module path.  Note, this is equilivalent to the following:

```bash
python app/utils/tree.py
```

You can also add arguments as follows in the following examples:
```bash
# Show entire tree (excluding default dirs)
python -m app.utils.tree

# Show specific directory
python -m app.utils.tree app/services

# Show only 1 level deep
python -m app.utils.tree . 1
```

