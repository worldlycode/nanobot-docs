# **Logging with Python's Standard Library**

**Date:** March 6, 2025   
**Author:** sam-i-am

<pre style="color: #3f51b5; font-size: 1.1rem;"><code>"Hello World! 🌐"</code></pre>

Logging, or tracking what happens as your code executes is pretty important to knowing what happened when things don't go as planned.  I have learned it is like inserting print statements in your code, but these statement can print out to the console (terminal or stdout), to a file, to an external logger (such as Logfire, which I will talk about in another post).  

The bottom line is that you can write an awful lot of code in a notebook, or in small modules, and not have to track things.  But when things start getting big, with thousands of lines of code, you really need to be able to log what is going on especially to find bugs etc.  

Plus, learning about logging makes you feel like a pro, like you have entered the big-time.  So lets get logging.  

## **Python's Logging Module**  

### Installing

There is nothing to install, the logging module comes standard with Python!  You just need to add the following at the top of your files.  
```python
import logging
```

### Setup Logging Config


So I started by following a few tutorials.  The one that helped me the most was from **mCoding** and called **Modern Python Logging**.  Click on thumbnail below to be redirected to the video.  

<a href="https://www.youtube.com/watch?v=9L77QExPmI0">
  <img src="https://img.youtube.com/vi/9L77QExPmI0/maxresdefault.jpg" alt="Video Title" style="width:100%; max-width:600px; border:2px solid #ccc; border-radius:10px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);">
</a>


