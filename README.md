# EX01 Developing a Simple Webserver

# Date:  19/09/2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''
<html>
<head>
<title>laptop</title></head>
<body>
  <p>Edition:Windows 13 Pro</p>
  <p>Version:24H2</p>
  <p>Processor:Intel i7-12700H</p>
  <p>Installed RAM: 24 GB</p>
  <p>System type: 128-bit Operating System</p>
</body>
</html>
'''
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content_type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2025-09-19 142552.png>)
![alt text](<Screenshot 2025-09-19 142710.png>)


# RESULT:
The program for implementing simple webserver is executed successfully.
