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
<h1>TOP FIVE PROGRAMMING LANGUAGE</h1>
<h1 style="color:pink">1.javscript</h1>
<p>JavaScript often abbreviated as JS, is a programming language that conforms to the
ECMAScript specification. JavaScript is high-level, often just-in-time compiled and
multi-paradigm. It has dynamic typing, prototype-based object-orientation and first-class
functions.
Alongside HTML and CSS, JavaScript is one of the core technologies of the World Wide Web.
Over 97% of websites use it client-side for web page behavior,often incorporating thirdparty libraries.All major web browsers have a dedicated JavaScript engine to execute the
code on the user's device.
As a multi-paradigm language, JavaScript supports event-driven, functional, and
imperative programming styles. It has application programming interfaces (APIs) for
working with text, dates, regular expressions, standard data structures, and the Document
Object Model (DOM).
The ECMAScript standard does not include any input/output (I/O), such as networking,
storage, or graphics facilities. In practice, the web browser or other runtime system
provides JavaScript APIs for I/O.
JavaScript engines were originally used only in web browsers, but they are now core
components of some servers and a variety of applications. The most popular runtime system
for this usage is Node.js.
Although there are similarities between JavaScript and Java, including language name,
syntax, and respective standard libraries, the two languages are distinct and differ
greatly in design.</p>
<h1 style="color.yellow">2.kotlin</h1>
<p>Kotlin is a cross-platform, statically typed, general-purpose programming language
with type inference. Kotlin is designed to interoperate fully with Java, and the JVM
version of Kotlin's standard library depends on the Java Class Library, but type
inference allows its syntax to be more concise. Kotlin mainly targets the JVM, but also
compiles to JavaScript (e.g., for frontend web applications using React) or native code
(via LLVM); e.g., for native iOS apps sharing business logic with Android apps.Language
development costs are borne by JetBrains, while the Kotlin Foundation protects the Kotlin
trademark.
On 7 May 2019, Google announced that the Kotlin programming language is now its preferred
language for Android app developers. Since the release of Android Studio 3.0 in October
2017, Kotlin has been included as an alternative to the standard Java compiler. The
Android Kotlin compiler produces Java 8 bytecode by default (which runs in any later
JVM), but lets the programmer choose to target Java 9 up to 16, for optimization, or
allows for more features; has bidirectional record class interoperability support for
JVM, introduced in Java 16, considered stable as of Kotlin 1.5.
Kotlin support for compilation directly to JavaScript (i.e., the classic back-end) is
considered stable since Kotlin 1.3 by its developers, while the new Kotlin/JS(IR) is in
beta as of version 1.5.30. The new optimized implementations of Kotlin/JVM(IR) and
Kotlin/JS (IR-based) were introduced in version 1.4. Kotlin/JVM(IR) is considered stable
as of the version 1.5 release. Kotlin/Native (for e.g. Apple silicon support) has been
considered beta since version 1.3.</p>
<h1 style="color:green">3.python</h1>
<p>Python is an interpreted high-level general-purpose programming language. Its design
philosophy emphasizes code readability with its use of significant indentation. Its
language constructs as well as its object-oriented approach aim to help programmers write
clear, logical code for small and large-scale projects.
Python is dynamically-typed and garbage-collected. It supports multiple programming
paradigms, including structured (particularly, procedural), object-oriented and
functional programming. It is often described as a "batteries included" language due to
its comprehensive standard library.
Guido van Rossum began working on Python in the late 1980s, as a successor to the ABC
programming language, and first released it in 1991 as Python 0.9.0. Python 2.0 was
released in 2000 and introduced new features, such as list comprehensions and a cycle-detecting garbage collection system (in addition to reference counting). Python 3.0 was
released in 2008 and was a major revision of the language that is not completely
backward-compatible. Python 2 was discontinued with version 2.7.18 in 2020.
Python consistently ranks as one of the most popular programming languages</p>
<h1 style="color:mediumblue">4.c++</h1>
<p>C++ is a general-purpose programming language created by Bjarne Stroustrup as an
extension of the C programming language, or "C with Classes". The language has expanded
significantly over time, and modern C++ now has object-oriented, generic, and functional
features in addition to facilities for low-level memory manipulation. It is almost always
implemented as a compiled language, and many vendors provide C++ compilers, including the
Free Software Foundation, LLVM, Microsoft, Intel, Oracle, and IBM, so it is available on
many platforms.
C++ was designed with an orientation toward system programming and embedded, resourceconstrained software and large systems, with performance, efficiency, and flexibility of
use as its design highlights. C++ has also been found useful in many other contexts, with
key strengths being software infrastructure and resource-constrained applications,
including desktop applications, video games, servers (e.g. e-commerce, web search, or
databases), and performance-critical applications (e.g. telephone switches or space
probes).
C++ is standardized by the International Organization for Standardization (ISO), with the
latest standard version ratified and published by ISO in December 2020 as ISO/IEC
14882:2020 (informally known as C++20). The C++ programming language was initially
standardized in 1998 as ISO/IEC 14882:1998, which was then amended by the C++03, C++11,
C++14, and C++17 standards. The current C++20 standard supersedes these with new features
and an enlarged standard library. Before the initial standardization in 1998, C++ was
developed by Danish computer scientist Bjarne Stroustrup at Bell Labs since 1979 as an
extension of the C language; he wanted an efficient and flexible language similar to C
that also provided high-level features for program organization. Since 2012, C++ has been
on a three-year release schedule[14] with C++23 as the next planned standard.</p>
<h1 style="color:violet">5.swift</h1>
<p>Swift is a general-purpose, multi-paradigm, compiled programming language developed by
Apple Inc. and the open-source community. First released in 2014, Swift was developed as
a replacement for Apple's earlier programming language Objective-C, as Objective-C had
been largely unchanged since the early 1980s and lacked modern language features. Swift
works with Apple's Cocoa and Cocoa Touch frameworks, and a key aspect of Swift's design
was the ability to interoperate with the huge body of existing Objective-C code developed
for Apple products over the previous decades. It is built with the open source LLVM
compiler framework and has been included in Xcode since version 6, released in 2014. On
Apple platforms, it uses the Objective-C runtime library, which allows C, Objective-C,
C++ and Swift code to run within one program.
Apple intended Swift to support many core concepts associated with Objective-C, notably
dynamic dispatch, widespread late binding, extensible programming and similar features,
but in a "safer" way, making it easier to catch software bugs; Swift has features
addressing some common programming errors like null pointer dereferencing and provides
syntactic sugar to help avoid the pyramid of doom. Swift supports the concept of protocol
extensibility, an extensibility system that can be applied to types, structs and classes,
which Apple promotes as a real change in programming paradigms they term "protocoloriented programming"
(similar to traits)</p>
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
