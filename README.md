# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display about top five programming languages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>TOP FIVE PROGRAMMING LANGUAGES</h1>
<h2>1.Javascript</h2>
JavaScript is a dynamic computer programming language.
JavaScript is always executed on client environment to save bandwidth and make execution process fast.
It is lightweight and most commonly used as a part of web pages, whose implementations allow client-side script to interact with the user and make dynamic pages.
It is an interpreted programming language with object-oriented capabilities.
<h2>2.C#</h2>
C# is pronounced as "C-Sharp". It is an object-oriented programming language provided by Microsoft that runs on .Net Framework.
C# is a modern, object-oriented and type-safe programming language which allows the user to create modular maintainable applications.
It provides language constructs to directly support these concepts, making C# a natural language in which to create and use software components.
By the help of C# programming language, we can develop different types of secured and robust applications.
<h2>3.Python</h2>
Python is a popular programming language created by Guido van Rossum, and released in 1991.
Python is used for server-side web development, software development, mathematics and system scripting.
Python is a general purpose language, meaning it can be used to create a variety of different programs and isn’t specialized for any specific problems.
It runs on an interpreter system, meaning that code can be executed as soon as it is written.
<h2>4.C++</h2>
C++ is a middle-level programming language developed which runs on a variety of platforms, such as Windows, Mac OS, and the various versions of UNIX.
It is the most widely used programming languages in application and system programming.
C++ is an object-oriented programming language which gives a clear structure to programs and allows code to be reused, lowering development costs.
It is portable and can be used to develop applications that can be adapted to multiple platforms.
<h2>5.Kotlin</h2>
Kotlin is a programming language widely used by Android developers everywhere.
Kotlin is an open source programming language that combines object-oriented programming and functional features into a unique platform.
This is relatively easy to adapt and better compatible with Java.
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
```

## OUTPUT:
![output 1](https://user-images.githubusercontent.com/94219798/154796831-b3b219ea-a136-4ceb-b7f3-d4176c400b46.png)

![output 2](https://user-images.githubusercontent.com/94219798/154796841-da1b99fa-f220-4beb-bfcf-c3751917fd59.png)

## RESULT:
The above simple webserver has been developed to display top five programming languages 
