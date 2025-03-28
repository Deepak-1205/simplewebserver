# EX01 Developing a Simple Webserver
## Date:24/03/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content= '''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>LAPTOP CONFIGURATION</h1>
<table BORDER="3" CELLSPACING="5" CELLPADDING="5">
    <TR>
        <TH>SYSTEM CONFIGURATION</TH>
        <TH>DESCRIPTION</TH>
    </TR>
    <TR>
        <TH>PROCESSOR</TH>
        <td><B>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</B></td>
    </TR>
    <TR>
        <TH>PRIMARY MEMORY</TH>
        <TD><B>16.0 GB (15.7 GB usable)</B></TD>
    </TR>
    <TR>
        <TH>SECONDARY MEMORY</TH>
        <TD><B>512 GB</B></TD>
    </TR>
    <TR>
        <TH>OPERATING SYSTEM</TH>
        <TD><B>Windows 11,64-bit operating system</B></TD>
    </TR>
    <TR>
        <TH>GRAPHICS CARD</TH>
        <TD><B>NVIDIA GeForce MX550</B></TD>
    </TR>
</table>
</body>
</html>
'''

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
![alt text](image1.png)


![alt text](image2.png)


## RESULT:
The program for implementing simple webserver is executed successfully.
