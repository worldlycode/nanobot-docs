# Hello World!
## Alex's Blog
### Hello everyone, I'm a nanoscience engineering doing my best impression of a computer scientist. I myself have built 4 different chat bots with varying degrees of success.

* V1: Before I knew a main.py from an __init__.py I used chat GPT and langchain to create a bot. I attempted to take the PDFs from the PROM Committee database, vectorized using ollama and put it in a Chromadb. It did not work very well, I think my chunk size was the entire document or something like that, if it's even possible. It was very slow and did not give good results
* V2: similar, but I moved over to a more powerful windows machine and trued using lighter (2billion parameter) models. I'd previouslt been using 8b which killed my little mac book
* V3: I figured, why re-invent the wheel, someone else must have an easy way to do chat bots. So I tried putting hundreds of PDFs into anything LLM. That also was very slow and didn't work so hot
* V4: Ok time to get serious. Got a NEON db, an OpenAI API key. Took the mas