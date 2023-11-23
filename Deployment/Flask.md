Build web applications
Flask is a lightweight web framework for Python.
Flask doesn’t come with all the bells and whistles of larger frameworks like Django.

### The Flask framework
[medium](https://towardsdatascience.com/flapjax-data-visualization-on-the-web-with-plotly-and-flask-465090fa3fba)
Flask is a minimalist framework for developing Web applications. 
In a Flask app, the web page typically is built from a template and data supplied by the Python code — this data can be text or graphics that form the content of the webpage. The result is sent to the user for display in the browser.

The diagram below shows the basic structure of an interactive app. When the app is running, the Python part executes on the server and passes data to the HTML which is running in the browser. The user input from the web page is passed back to the Python code which may then send more data to update the HTML with new content — a new chart that has been selected by the user, for example.
![diagram](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*MpyyvM3YR_LYuxWxvQJWzQ.png)
### A Flask project
A Flask application will normally consist of at least two files: a Python app and an HTML template.

The directory structure for a simple app
```python
/project_name  
|--- app.py  
|  
|--- /templates  
|  
|--- index.html
```