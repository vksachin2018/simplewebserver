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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
    <table>
        <tr>
            <th>Rank</th>
            <th>Company</th>
            <th>Revenue</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Microsoft</td>
            <td>$86.8</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Oracle</td>
            <td>$37.1</td>
        </tr>
        <tr>
            <td>3</td>
            <td>SAP</td>
            <td>$20.9</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Symantec</td>
            <td>$6.8</td>
        </tr>
        <tr>
            <td>5</td>
            <td>VMware</td>
            <td>$5.2</td>
        </tr>
    </table>
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
![image](https://github.com/vksachin2018/simplewebserver/assets/149366019/c690d7bc-41d9-4556-ab6f-73d5c8a2ac51)
![image](https://github.com/vksachin2018/simplewebserver/assets/149366019/c8aea488-782b-4c3c-a7ab-ab06d11ead46)



## RESULT:
The program for implementing simple webserver is executed successfully.
