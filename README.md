# EX01 Developing a Simple Webserver

## Date:29.09.2026

## AIM:
To develop a simple webserver to serve html pages and display the Windows Specifications of your Laptop.

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

from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <head>
        <title>sample web page</title>
    </head>
        <body>
            <h1 bgcolor="red">Name=Gokul S.P </h1>
            <h2 bgcolor="red">REF NO=26019369</h2>
            <table border="2" bgcolor="Purple" cellspacing="10" cellpadding="10" >
                <caption>LAPTOP CONFIGURATION</caption>
                <tr>
                    <th bgcolor="beige">s.no</td>
                    <th bgcolor="beige">device type</td>
                    <th bgcolor="beige">device info</td>
                </tr>
                <tr>
                    <td bgcolor="beige">1</td>
                    <td bgcolor="beige" align="center">Device Name</td>
                    <td bgcolor="beige" align="center">TL15-53M-G2</td>
                </tr>
                <tr>
                    <td bgcolor="beige">2</td>
                    <td bgcolor="beige" align="center">Processor</td>
                    <td bgcolor="beige" align="center">Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
                </tr>
                <tr>
                    <td bgcolor="beige">3</td>
                    <td bgcolor="beige" align="center">Istalled RAM</td>
                    <td bgcolor="beige" align="center">16.0 GB (15.7 GB usable)</td>
                </tr>
                <tr>
                    <td bgcolor="beige">4</td>
                    <td bgcolor="beige" align="center">Graphics Card</td>
                    <td bgcolor="beige" align="center">intel(R) Graphics (128 MB)</td>
                </tr>
                <tr>
                    <td bgcolor="beige">5</td>
                    <td bgcolor="beige" align="center">Storage</td>
                    <td bgcolor="beige" align="center">121 GB of 477 GB used</td>
                </tr>
                <tr>
                    <td bgcolor="beige">6</td>
                    <td bgcolor="beige" align="center">Device ID</td>
                    <td bgcolor="beige" align="center">F56949A2-B4DC-4F59-B8C4-89B698EB62DF</td>
                </tr>
                <tr>
                    <td bgcolor="beige">7</td>
                    <td bgcolor="beige" align="center">product ID</td>
                    <td bgcolor="beige" align="center">00342-42954-11443-AAOEM</td>
                </tr>
                <tr>
                    <td bgcolor="beige">8</td>
                    <td bgcolor="beige" align="center">system type</td>
                    <td bgcolor="beige" align="center">64-bit operating system, x64-based processor</td>
                </tr>
                <tr>
                    <td bgcolor="beige">9</td>
                    <td bgcolor="beige" align="center">pen and touch support</td>
                    <td bgcolor="beige" align="center">No pen or touch input is available for this display</td>
                </tr>
            </table>

        </body>
        
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Client request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my own webserver is running successfully...")
httpd.serve_forever()

```


## OUTPUT:
webpage
![alt text](image.png)




![alt text](<Screenshot 2026-10-24 142418.png>)




## RESULT:
The program for implementing simple webserver is executed successfully.
