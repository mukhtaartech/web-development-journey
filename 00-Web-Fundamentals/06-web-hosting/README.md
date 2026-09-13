# 🌐 06 — Web Hosting

> Learning how websites are stored, served, and made accessible on the internet.

---

## 📖 Introduction

A website is made up of files such as:

* HTML
* CSS
* JavaScript
* Images
* Videos
* Fonts
* Server-side code
* Databases

These files need to be stored somewhere so that users can access the website through the internet.

**Web hosting** is the service that provides the server infrastructure where a website's files and applications can live and be accessed by users.

In this topic, I am learning how web hosting works, the different types of hosting, how domains connect to hosting, and what happens when someone visits a hosted website.

---

## 1️⃣ What Is Web Hosting?

Web hosting is a service that provides the resources needed to make a website available on the internet.

A simplified example:

```text
Website Files
     │
     ▼
┌─────────────────┐
│   Web Server    │
│                 │
│ HTML            │
│ CSS             │
│ JavaScript      │
│ Images          │
└────────┬────────┘
         │
         ▼
      Internet
         │
         ▼
      Visitors
```

Instead of keeping a website only on my personal computer, the website can be placed on a server that is connected to the internet.

---

## 2️⃣ What Is a Web Server?

A **web server** is a computer system or software responsible for receiving and responding to web requests.

For example:

```text
Browser
   │
   │ HTTP Request
   ▼
Web Server
   │
   │ HTTP Response
   ▼
Browser
```

When a browser requests a webpage, the web server processes the request and sends the required resources back.

Common web server software includes:

| Web Server | Description                                   |
| ---------- | --------------------------------------------- |
| Apache     | Popular open-source web server                |
| Nginx      | High-performance web server and reverse proxy |
| IIS        | Microsoft's web server                        |
| Caddy      | Modern web server with simple configuration   |

---

## 3️⃣ Hosting vs Web Server

These terms are related but are not exactly the same.

### Web Server

A web server is the software or system that handles web requests.

### Web Hosting

Web hosting is the service/infrastructure that provides a place and resources for a website or application to run.

A simple way to think about it:

```text
Hosting
   │
   ├── Server Hardware
   ├── Storage
   ├── Network Connection
   ├── Operating System
   └── Server Software
            │
            ▼
       Website/Application
```

---

## 4️⃣ Where Are Websites Hosted?

Websites can be hosted on different types of infrastructure.

For example:

```text
                    Internet
                       │
        ┌──────────────┼──────────────┐
        │              │              │
        ▼              ▼              ▼
   Shared Hosting    VPS/Cloud     Dedicated Server
        │              │              │
        ▼              ▼              ▼
     Website        Website        Website
```

The appropriate option depends on the website's requirements, traffic, budget, and technical needs.

---

## 5️⃣ Shared Hosting

With **shared hosting**, multiple websites use resources on the same physical server.

```text
             Physical Server
        ┌──────────────────────┐
        │                      │
        │ Website A            │
        │ Website B            │
        │ Website C            │
        │ Website D            │
        │                      │
        └──────────────────────┘
```

### Advantages

* Usually inexpensive
* Easy to get started
* Often includes a control panel
* Good for small websites

### Disadvantages

* Resources are shared
* Less control over the server
* Performance can be affected by other workloads
* Limited configuration compared with VPS or dedicated servers

Shared hosting is commonly suitable for beginners and smaller websites.

---

## 6️⃣ VPS Hosting

**VPS** stands for **Virtual Private Server**.

A physical server can be divided into multiple virtual servers.

```text
             Physical Server
        ┌──────────────────────┐
        │      Hypervisor      │
        ├──────────┬───────────┤
        │   VPS 1  │   VPS 2   │
        │          │           │
        ├──────────┼───────────┤
        │   VPS 3  │   VPS 4   │
        └──────────┴───────────┘
```

Each VPS can have its own operating system and configuration.

### Advantages

* More control
* More predictable resources
* Can install custom software
* Suitable for more advanced applications

### Disadvantages

* More expensive than basic shared hosting
* Requires more technical knowledge
* Server administration may be necessary

---

## 7️⃣ Dedicated Server

A **dedicated server** gives a customer an entire physical server.

```text
        ┌──────────────────────┐
        │   Dedicated Server   │
        │                      │
        │     Your Website     │
        │     Your Apps        │
        │     Your Services    │
        └──────────────────────┘
```

The customer does not share the physical server with other customers.

### Advantages

* High control
* Dedicated hardware resources
* Can handle demanding workloads
* Extensive configuration possibilities

### Disadvantages

* More expensive
* Requires server administration skills
* Often unnecessary for small websites

---

## 8️⃣ Cloud Hosting

Cloud hosting uses computing resources provided through a cloud infrastructure.

Instead of thinking about one physical server:

```text
        One Server
            │
            ▼
         Website
```

Cloud infrastructure can involve multiple interconnected resources:

```text
             Cloud Infrastructure
          ┌─────────┬─────────┬─────────┐
          │ Server  │ Server  │ Server  │
          │   A     │   B     │   C     │
          └────┬────┴────┬────┴────┬────┘
               │         │         │
               └─────────┼─────────┘
                         │
                      Website
```

Cloud platforms can provide services such as:

* Virtual machines
* Storage
* Databases
* Networking
* Load balancing
* Content delivery
* Serverless computing

---

## 9️⃣ Static Website Hosting

A **static website** mainly consists of files that can be served directly to visitors.

For example:

```text
website/
│
├── index.html
├── about.html
├── style.css
├── script.js
└── images/
```

The server can simply return these files when requested.

```text
Browser
   │
   │ GET /index.html
   ▼
Server
   │
   │ index.html
   ▼
Browser
```

Static hosting is commonly suitable for:

* Portfolio websites
* Documentation
* Landing pages
* Simple business websites
* Blogs generated as static files

---

## 🔟 Dynamic Website Hosting

A dynamic website can generate content based on requests, users, databases, or other application logic.

For example:

```text
Browser
   │
   ▼
Web Server
   │
   ▼
Application
   │
   ▼
Database
   │
   ▼
Application
   │
   ▼
Web Server
   │
   ▼
Browser
```

Examples include websites with:

* Login systems
* User accounts
* Shopping carts
* Dashboards
* Online booking
* Databases
* Personalized content

Technologies used for dynamic applications can include:

* PHP
* Node.js
* Python
* C#
* Java
* Ruby

---

## 1️⃣1️⃣ Domain Name + Hosting

A domain name and web hosting perform different jobs.

### Domain

The domain is the human-readable address.

Example:

```text
example.com
```

### Hosting

Hosting provides the infrastructure where the website runs.

```text
Domain
  │
  │ DNS
  ▼
Server IP Address
  │
  ▼
Web Hosting
  │
  ▼
Website
```

So:

> **Domain = address**

> **Hosting = place where the website lives**

---

## 1️⃣2️⃣ How DNS Connects the Domain to Hosting

The process can be simplified as:

```text
User enters:

www.example.com
        │
        ▼
      DNS
        │
        ▼
Server IP Address
        │
        ▼
   Web Server
        │
        ▼
    Website
```

DNS records can point a domain or subdomain toward the appropriate server or service.

For example, an `A` record can associate a hostname with an IPv4 address.

---

## 1️⃣3️⃣ What Happens When I Visit a Hosted Website?

A simplified process looks like this:

```text
1. Enter URL
      │
      ▼
2. Browser checks DNS information
      │
      ▼
3. DNS resolves the hostname
      │
      ▼
4. Browser connects to the server
      │
      ▼
5. HTTP/HTTPS request is sent
      │
      ▼
6. Server processes the request
      │
      ▼
7. Server sends a response
      │
      ▼
8. Browser downloads resources
      │
      ▼
9. Browser renders the webpage
```

This connects several concepts I have already learned:

```text
Domain Names
      │
      ▼
     DNS
      │
      ▼
   Hosting
      │
      ▼
 Web Server
      │
      ▼
HTTP / HTTPS
      │
      ▼
   Browser
```

---

## 1️⃣4️⃣ HTTP and HTTPS

Websites commonly communicate using **HTTP** or **HTTPS**.

### HTTP

HTTP stands for:

**Hypertext Transfer Protocol**

It defines how web clients and servers communicate.

### HTTPS

HTTPS is HTTP secured using encryption through TLS.

```text
HTTP
Browser ───────────────► Server
       Request

HTTPS
Browser ═══════════════► Server
       Encrypted
       Connection
```

HTTPS helps protect data exchanged between the browser and server from being read or modified by unauthorized parties in transit.

---

## 1️⃣5️⃣ Hosting a Website From My Own Computer

It is technically possible to host a website from a personal computer.

For example:

```text
Internet
    │
    ▼
Router
    │
    ▼
My Computer
    │
    └── Web Server
             │
             ▼
          Website
```

However, several things need to be considered:

* Public IP address
* Router configuration
* Port forwarding
* Firewall rules
* Security
* Uptime
* ISP restrictions
* Domain/DNS configuration
* Server maintenance

For learning, running a local web server is useful.

For production websites, managed hosting or cloud infrastructure is usually more practical.

---

## 1️⃣6️⃣ Localhost

`localhost` refers to the local computer.

The commonly used IPv4 address is:

```text
127.0.0.1
```

For example:

```text
http://localhost
```

or:

```text
http://127.0.0.1
```

This allows me to test web applications locally without making them publicly accessible.

---

## 1️⃣7️⃣ Ports

A server can provide different services through different network ports.

Common web ports include:

| Port | Common Use |
| ---: | ---------- |
|   80 | HTTP       |
|  443 | HTTPS      |

A development server might use a port such as:

```text
http://localhost:3000
```

Here:

```text
localhost → Computer
3000      → Port
```

The port helps the operating system determine which service should receive the network connection.

---

## 1️⃣8️⃣ Web Hosting Components

A hosting environment can contain many different components.

```text
                  Web Hosting
                       │
       ┌───────────────┼───────────────┐
       │               │               │
       ▼               ▼               ▼
    Storage          Server          Network
       │               │               │
       ▼               ▼               ▼
Website Files      Web Server       Internet
                       │
                       ▼
                  Application
                       │
                       ▼
                    Database
```

Depending on the hosting service, I may also have:

* SSL/TLS certificates
* Backups
* Email services
* Databases
* DNS management
* Firewalls
* Monitoring
* CDN integration
* Control panels

---

## 1️⃣9️⃣ Important Hosting Terms

| Term             | Meaning                                                         |
| ---------------- | --------------------------------------------------------------- |
| Hosting          | Infrastructure used to make a website/application available     |
| Web Server       | Software/system that handles web requests                       |
| VPS              | Virtual Private Server                                          |
| Dedicated Server | Physical server dedicated to one customer                       |
| Cloud Hosting    | Hosting using cloud infrastructure                              |
| Static Website   | Website primarily served from static files                      |
| Dynamic Website  | Website whose content can be generated or processed dynamically |
| Storage          | Space used to store website/application data                    |
| Bandwidth        | Amount of data that can be transferred                          |
| Uptime           | How consistently a service remains available                    |
| SSL/TLS          | Technology used to secure HTTPS connections                     |
| CDN              | Content Delivery Network                                        |
| Control Panel    | Interface used to manage hosting                                |
| IP Address       | Network address used to identify a host/interface               |
| Port             | Logical endpoint used by network services                       |

---

## 2️⃣0️⃣ Hosting vs Domain vs DNS

These concepts can be confusing at first.

| Concept    | Main Purpose                            |
| ---------- | --------------------------------------- |
| Domain     | Human-readable website address          |
| DNS        | Connects names to network information   |
| Hosting    | Provides infrastructure for the website |
| Web Server | Handles web requests                    |
| Browser    | Requests and displays web content       |

A simplified relationship:

```text
             DOMAIN
                │
                ▼
               DNS
                │
                ▼
          Server / Service
                │
                ▼
             HOSTING
                │
                ▼
           WEB SERVER
                │
                ▼
             WEBSITE
                │
                ▼
            BROWSER
```

---

## 2️⃣1️⃣ Practical Learning

I can practice hosting concepts by creating a simple website:

```text
my-website/
│
├── index.html
├── style.css
└── script.js
```

Then I can run it locally using a development server.

For example:

```text
Browser
   │
   ▼
localhost
   │
   ▼
Local Web Server
   │
   ▼
index.html
```

Later, I can learn how to deploy the same project to a real hosting environment.

---

## 2️⃣2️⃣ What I Learned

Through this topic, I learned:

* What web hosting is
* What a web server does
* The difference between hosting and a web server
* Shared hosting
* VPS hosting
* Dedicated servers
* Cloud hosting
* Static website hosting
* Dynamic website hosting
* How domains and hosting work together
* How DNS connects a domain to a server/service
* The basic HTTP/HTTPS process
* What localhost means
* The purpose of ports
* Basic hosting infrastructure
* Why hosting requirements depend on the application

Most importantly, I learned that a website is not simply "on the internet."

There is an infrastructure behind it:

```text
Domain
   ↓
DNS
   ↓
Network
   ↓
Server
   ↓
Hosting Environment
   ↓
Web Server
   ↓
Application / Files
   ↓
Browser
```

---

## 🤔 Questions I Want to Explore Next

* How do I actually deploy a website to a hosting server?
* What is a control panel such as cPanel?
* What is a CDN?
* What is a reverse proxy?
* How does Nginx work?
* How does Apache work?
* How do SSL/TLS certificates work?
* What is a VPS and how do I configure one?
* How does cloud hosting work?
* How do websites handle thousands or millions of visitors?
* What is load balancing?
* How do databases work with hosted applications?

---

## 📈 Progress

**Stage:** Web Fundamentals

**Topic:** Web Hosting

**Status:** 🟡 Learning

**Previous:** [DNS](../05-dns/)

**Next:** HTTP & HTTPS

---

> 💻 **Learning by understanding the infrastructure behind the web — not just writing the code.**

---

