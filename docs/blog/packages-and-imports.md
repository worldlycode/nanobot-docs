# Managing Packages and Imports

**Date:** April 25, 2025  
**Author:** sam-i-am

<pre style="color: #3f51b5; font-size: 1.1rem;"><code>"Hello World! 🌐"</code></pre>

## Cleaning up your virrual environment

One always wants to would in a development environment.  most often this is done by creating an environment that your codebase depends on using something like `venv`, which is what we are currently using in our projects.  

One of the issues is that every time you do a `pip install [package name]` it will also install all of the dependencies that that package depends on.  However, in the requirements.txt file it is best practice to only list the top level dependencies, and let pip resolve and install all of the subdependencies.  

If you are like me and have a requirements files that includes **all** of the dependencies including the sub-dependencies, and need to clean all of that up, you can do the following:

1. Create a backup of your current requirements.txt file
```bash
cp requirements.txt requirements.txt.bak
```
2. Install pipreqs in your activated virtual environment
```bash
pip install pipreqs
```
3. Run pipreqs from the project root
```bash
pipreqs . --force
```

## Importing and using local packages

This is a good reference for importing packages:

<a href="https://www.youtube.com/watch?v=VEbuZox5qC4">
  <img src="https://www.youtube.com/watch?v=VEbuZox5qC4/sddefault.jpg" alt="Video Title" style="width:100%; max-width:600px; border:2px solid #ccc; border-radius:10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</a>

https://www.youtube.com/watch?v=VEbuZox5qC4

Tech with Tim


from the chunking.py file in the document_conversion folder, I want to import the Chunks and ChunkMetadata classes from the models.db_schemas module.

```python
import sys
import os
parent_dir = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
sys.path.append(parent_dir)
from models.db_schemas import Chunks, ChunkMetadata
```


1. os.path.abspath(__file__):
This gets the absolute path of the current file (chunking.py).
2. os.path.dirname():
Called twice to move up two directory levels, reaching the root of your project (nanobot-poc).
3. sys.path.append(parent_dir):
Adds the parent directory to sys.path, which is the list of directories Python searches for modules.
By including the parent directory, Python can now find models.db_schemas because models is a sibling directory to document_conversion.
4. Import Statement:
With the parent directory in sys.path, the import from models.db_schemas import Chunks, ChunkMetadata works because Python can now locate the models directory.


This method effectively adjusts the module search path at runtime, allowing you to import modules from sibling directories.


