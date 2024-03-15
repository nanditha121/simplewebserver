# EX01 Developing a Simple Webserver
## Date:27-02-2024

## AIM:
To develop a simple webserver to serve html pages.

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

from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>IT companies in India based on revenue</title>
    </head>
<body>
<table cellspacing="2" cellpadding="4" border="2">
           <h1 allign="center">IT companies in India based on revenue<h1>
           <tr >
           <th>RANK</th>
           <th>COMPANY NAME</th>
           <th>REVENUE</th>
           </tr>
           <tr>
           <td >1.</td>
           <td >TATA CONSULTANCY SERVICES</td>
           <td>195,772</td>
           </tr>
           <tr>
           <td >2.</td>
           <td >INFOSYS</td>
           <td>123,936</td>
           </tr>
           <tr>
           <td>3.</td>
           <td>HCL TECHNOLOGIES</td>
           <td>85,651</td>
           </tr>
           <tr>
           <td >4.</td>
           <td>WIPRO</td>
           <td>79,903</td>
           </tr>
           <tr>
           <td>5.</td>
           <td>HCL TECHNOLOGIES</td>
           <td>76,306</td>
           </tr>
           </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![alt text](<Screenshot (6).png>)

![alt text](<Screenshot (7).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
