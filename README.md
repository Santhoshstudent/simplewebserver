# EX01 Developing a Simple Webserver
## Date:

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<table border ="2" cellspacing ="10" cellpadding = "6" align = "Center">
<caption> TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES </caption>
<tr>
<th> S.No </th>
<th> Company </th>
<th> Revenue </th>
</tr>
<tr>
<td> 1. </td>
<td> tcs </td>
<td> 265 Billion </td>
</tr>
<tr>
<td> 2. </td>
<td> HCL </td>
<td> 29.6 Billion </td>
</tr>
<tr>
<td> 3. </td>
<td> HP </td>
<td> 29.1 Billion </td>
</tr>
<tr>
<td> 4. </td>
<td> RIL </td>
<td> 456 Billion </td>
</tr>
<tr>
<td> 5. </td>
<td> OYO </td>
<td> 5.6 Billion </td>
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
![Screenshot 2024-03-25 082724](https://github.com/Santhoshstudent/simplewebserver/assets/145446853/df097e71-565e-45be-9bf3-a46cd98b0807)




## RESULT:
The program for implementing simple webserver is executed successfully.
