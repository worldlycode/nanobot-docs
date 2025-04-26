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

To print the entire tree structure you would use:

```bash
python -m app.utils.tree
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


## `logging_examples.py`

This code is essentially a test script to test the logging functionality and configuration and will populate test log files in the following directory 

```bash
nanobot-poc/
├── logs/
```
It is fun from the terminal when in the root `nanobot-poc` directory with the following command
```bash
python -m app.utils.logging_examples
```

I think eventually we may want to move this to test functionality

