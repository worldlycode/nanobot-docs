# Setting up Pydantic Logfire

Logfire by Pydantic is used to record the interaction between the LLM and the application.  Using Logfire one is able to see what is being passed to the model, and what the model is returning.  Additionally you can also see the length of timeeach call takes.  

To Use the Nanobot-Dev codebase without modification you will need to configure a Logfire account.  The can be used at no charge for a ridicolous number of calls, (10 million free spans/metrics per month).  

Follow these steps:

1. Go to the main website at https://pydantic.dev/logfire and create an account
2. Log into Logfire
3. Go to the Projects Page and creeate a new project.  
4. Generate a `write token` and save it for future use
5. Copy the logfire token into your `.eve` file.  Do not use brackets or quotes or spaces.

```txt
LOGFIRE_TOKEN=[YOUR_TOKEN_HERE] 
```
This is what the project page looks like. 

![logfire_project_page](../assets/images/logfire_project_view.png)

In order to see the live updates you will want to click on the `Live` tab at the top toolbar of the page.  Each time you make an LLM Call from your application, it will update here in the live view.  You can also search all history going up to 30 days back.

A call in the live view looks like the following image.

![logfire_project_page](../assets/images/logfire_live_view.png)
