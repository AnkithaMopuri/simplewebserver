# EX01 Developing a Simple Webserver
## Date: 27-02-2024

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
content = """<html>
<head>
<title>Top software companies in revenue</title>
</head>
<body>
<h1 align="left">Top Software companies in revenue</h1>
<table border="2" cellspacing="5" cellpadding="5" width="40" height="50">
<tr>
<th>Rank</th>
<th>Company</th>
<th>Revenue</th>
<th>Nationality</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft</td>
<td>57.9</td>
<td>USA</td>
</tr>
<tr>
<td>2</td>
<td>Oracle</td>
<td>21.0</td>
<td>USA</td>
</tr>
<tr>
<td>3</td>
<td>SAP</td>
<td>16.1</td>
<td>Germany</td>
</tr>
<tr>
<td>4</td>
<td>Computer Associates</td>
<td>4.2</td>
<td>USA</td>
</tr>
<tr>
<td>5</td>
<td>Adobe</td>
<td>3.4</td>
<td>USA</td>
</tr>
<tr>
<td>6</td>
<td>Electronic Arts</td>
<td>3.2</td>
<td>USA</td>
</tr>
<tr>
<td>7</td>
<td>Amdocs</td>
<td>2.9</td>
<td>USA</td>
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
![alt text](<Screenshot (213)-2.png>)
![alt text](<Screenshot (212)-1.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
