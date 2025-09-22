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
from http.server import HTTPServer, BaseHTTPRequestHandler

Content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Protocol Suite - TCP/IP Model</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f4f4f4;
    }
    h1 {
      color: #333;
    }
    .layer {
      border: 1px solid #ccc;
      background-color: #fff;
      margin: 15px auto;
      padding: 20px;
      width: 60%;
      box-shadow: 2px 2px 5px rgba(0,0,0,0.1);
    }
    .layer h2 {
      color: #0066cc;
    }
    .protocols {
      margin-top: 10px;
      color: #333;
    }
  </style>
</head>
<body>
  <h1>TCP/IP Protocol Suite</h1>

  <div class="layer">
    <h2>Application Layer</h2>
    <div class="protocols">HTTP, FTP, DNS, SMTP, POP3, SNMP</div>
  </div>

  <div class="layer">
    <h2>Transport Layer</h2>
    <div class="protocols">TCP, UDP</div>
  </div>

  <div class="layer">
    <h2>Internet Layer</h2>
    <div class="protocols">IP, ICMP, ARP</div>
  </div>

  <div class="layer">
    <h2>Network Access Layer</h2>
    <div class="protocols">Ethernet, Wi-Fi, PPP</div>
  </div>

</body>
</html>
"""

class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("GET request received...")
        self.send_response(200)
        self.send_header("Content-Type", "text/html")  # ✅ Corrected this line
        self.end_headers()
        self.wfile.write(Content.encode())

print("This is my webserver")
server_address = ('', 8000)
httpd = HTTPServer(server_address, Myserver)
httpd.serve_forever()
```
# OUTPUT:
<img width="992" height="334" alt="image" src="https://github.com/user-attachments/assets/90fa0eb3-c1f1-4266-ac42-ca99d0f67c13" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6010ab53-679f-4e58-9b62-eda67701c7b3" />




# RESULT:
The program for implementing simple webserver is executed successfully.
