# NAME: R.SABARINATH
# REGISTER NUMBER: 212223100046

# Echoserver
Echo server and client using python socket
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

**Step 1:** HTML content creation is done for displaying in the browser.

**Step 2:** Design of webserver workflow is completed with request and response handling.

**Step 3:** Implementation is done using Python code with HTTPServer and handler.

**Step 4:** HTML pages are served by running the server on localhost with port 8000.

**Step 5:** Webserver is tested by opening the browser and entering `http://127.0.0.1:8000`.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

# HTML content that the server will return
content = '''<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Hello Web Server</h1>
<h2>Top Five Web Application Development Frameworks</h2>
<h3>1. Django</h3>
<h3>2. MEAN Stack</h3>
<h3>3. React</h3>
</body>
</html>'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print(f"GET request from {self.client_address}")
        self.send_response(200)
        self.send_header("Content-Type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode('utf-8'))

if __name__ == "__main__":
    server_address = ('127.0.0.1', 8000)  
    httpd = HTTPServer(server_address, MyServer)
    print(f"Serving on http://{server_address[0]}:{server_address[1]}")
    httpd.serve_forever()

```
##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
### SERVER OUTPUT:
![WhatsApp Image 2025-08-09 at 10 41 19_8311b65d](https://github.com/user-attachments/assets/c064e3b9-fabf-4e6b-a0c7-cc63e6deb53a)


### CLIENT OUTPUT:
![WhatsApp Image 2025-08-09 at 10 56 59_2851eaeb](https://github.com/user-attachments/assets/238086d2-e427-40da-9616-007451413a5c)


## RESULT:
The program is executed succesfully
