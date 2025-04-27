# Understanding IBM's Docling

**Date:** April 25, 2025  
**Author:** sam-i-am

<pre style="color: #3f51b5; font-size: 1.1rem;"><code>"Hello World! 🌐"</code></pre>

I am trying to understand the Docling Package, as it is powerful but somewhat complicated under the hood.  The first thing I am beginning to understand is that Docling is the open source itteration of a different tool it released in 2022, called the **Deep Search for Discovery Toolkit** (DS4SD).  Seep Search was the original solution for PDF documents, and now in 2024 they released docling in the [Arxiv paper found at this link](https://arxiv.org/pdf/2501.17887).  

## PDF Conversions

This is perhaps the main reason to use Docling.  Most python package PDF converters handle the text of a PDF document, and possibly even try to identify tables and images. But the latter in my experience they do not do well.  In addition to that the traditional packages do not capture the context, so they are not able to handle the chunking of "Sections" properly.  This means they may not know that a paragraph belongs to a particular section, and perhaps should not be spilt etc.  

In any event, these are thisngs that Docling does very well, expecially for something that runs locally and free of charge.  (There are models such as Unstructures, Azure Intellisense, etc that also do a reasonable job but cost money).  Lastly there are methods that are rather state of the art that use MMLM with vision capabilities, to take in each PDF page as an image and then using these models to identify the areas and components of each page.  

However, with Docling, IBM has trained two models that run locally (either on CPU or with GPU assist) These models are found on [Hugging Face](https://huggingface.co/ds4sd/docling-models) and include:

* **Layout Model**: The layout model will take an image from a page and apply RT-DETR model ([RT-DETR is an object detection model](https://huggingface.co/docs/transformers/en/model_doc/rt_detr) that stands for “Real-Time DEtection Transformer.”) in order to find different layout components. It currently detects the labels: Caption, Footnote, Formula, List-item, Page-footer, Page-header, Picture, Section-header, Table, Text, Title. As a reference (from the [DocLayNet-paper](https://arxiv.org/pdf/2206.01062)), this is the performance of standard object detection methods on the DocLayNet dataset compared to human evaluation 

* **Table Former**: The tableformer model will identify the structure of the table, starting from an image of a table. It uses the predicted table regions of the layout model to identify the tables. Tableformer has SOTA table structure identification.  The [Arxiv paper can be found at the following link](https://arxiv.org/pdf/2203.01017).  

So we have a lot to figure out here.  But I am convinced this is the way to go for an out-of-the-box methodology.  There is still a learning curve to optimize how to use the chunking module to optimize the vector embeddings.  