# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>NAME:Django</h1>
<h2>This is Web Application Framework written in python</h2>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
##Server side output
![WhatsApp Image 2023-01-09 at 11 17 42](https://user-images.githubusercontent.com/119404426/211248362-71a466df-f5ed-4ef8-a0af-bbd959c42845.jpg)
##Client side output
![WhatsApp Image 2023-01-09 at 11 17 42](https://user-images.githubusercontent.com/119404426/211248401-addd528c-fce7-47da-aaf7-f61ed11c0d3e.jpg)

## RESULT:
The program is executed succesfully
