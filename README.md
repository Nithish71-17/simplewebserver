# EX01 Developing a Simple Webserver
## Date:25.9.24

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

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1><center>My Laptop Configuration Details</center></h1>
   <table border="1" cellpadding="10" align="center">
        <tr>
            <th bgcolor="yellow">Specification</th>
            <th bgcolor="red">Details</th>
        </tr>
        <tr>
            <td>Model</td>
            <td>Lenovo ThinkPad i5</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core i5</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>8GB</td>
        </tr>
        <tr>
            <td>Storage</td>a
            <td>256GB SSD</td>
        </tr>
        <tr>
            <td>Graphics</td>
            <td>Integrated Intel UHD Graphics</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>14-inch FHD (1920 x 1080)</td>
        </tr>
        <tr>
            <td>Operating System</td>
            <td>Windows 10</td>
        </tr>
        <tr>
            <td>Colours available</td>
            <td>Black,White,Grey</td>
        </tr>
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
![Screenshot 2024-10-26 133653](https://github.com/user-attachments/assets/bd1ed766-453f-49d5-a4d4-ecd94ae0fc7c)

![Screenshot 2024-10-26 133645](https://github.com/user-attachments/assets/3aa36318-b81c-416f-832a-a6479612c10e)

## RESULT:
The program for implementing simple webserver is executed successfully.
