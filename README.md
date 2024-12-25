# EX01 Developing a Simple Webserver
## Date:26/10/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content="""
<html>
<title>SYSTEM SPECIFICATIONS</title>
<body>
<table border="2" cellspacing="10"cellpadding="6">
<caption>SOFTWARE AND HARDWARE INFORMATION</caption>
<tr>
<th>SNO</th>
<th>specification</th>
<th>value</th>
</tr>
<tr>
<th>1</th>
<th>RAM</th>
<th>16 GB</th>
</tr>
<tr>
<th>2</th>
<th>OS</th>
<th>WINDOWS</th>
</tr>
<tr>
<th>3</th>
<th>PROCESSOR</th>
<th>i5</th>
</tr>
<body>
<html>

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:
![alt text](<localhost 1.png>)
![alt text](<Screenshot 2024-10-27 112452.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
