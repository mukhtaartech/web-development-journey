🌐 04 — Domain Names

📖 Introduction

After learning about websites, the client-server model, and web browsers, the next concept I want to understand is domain names.

Whenever I visit a website, I usually type a human-readable name such as:

google.com
github.com
youtube.com

Instead of typing an IP address.

Domain names make it easier for humans to access websites without having to remember numerical IP addresses.

---

1️⃣ What Is a Domain Name?

A domain name is a human-readable name used to identify a location or service on the Internet.

For example:

google.com

is a domain name.

Computers communicate across networks using IP addresses, but remembering an IP address for every website would be difficult.

Instead of:

142.250.x.x

I can use:

google.com

The Domain Name System (DNS) helps connect the domain name to the appropriate IP address.

---

2️⃣ Why Do We Need Domain Names?

Imagine having to remember an IP address for every website I visit.

Instead of:

Website A → 192.0.2.10
Website B → 192.0.2.20
Website C → 192.0.2.30

I can use:

Website A → website-a.com
Website B → website-b.com
Website C → website-c.com

Domain names make the Internet easier for humans to use.

---

3️⃣ Domain Name vs IP Address

A domain name and an IP address are not the same thing.

Domain Name

example.com

Human-friendly.

IP Address

93.184.216.34

Network address used to reach a destination.

A simplified relationship is:

Domain Name
     │
     │ DNS
     ▼
IP Address
     │
     ▼
Server

---

4️⃣ What Does a Domain Name Look Like?

Consider:

www.example.com

This can be broken down into different parts.

www.example.com
│   │       │
│   │       └── Top-Level Domain
│   │
│   └────────── Second-Level Domain
│
└────────────── Subdomain

However, "www" is not actually required for a website to work.

For example:

example.com
www.example.com

can be configured to reach the same website or different services.

---

5️⃣ Top-Level Domain (TLD)

The final part of a domain name is called the Top-Level Domain, or TLD.

Examples include:

.com
.org
.net
.edu
.gov

There are also country-code TLDs:

.ke
.uk
.us
.id
.in

For example:

example.com
       ↑
      TLD

And:

example.ke
       ↑
      TLD

---

6️⃣ Second-Level Domain

Consider:

example.com

The word:

example

is the second-level domain.

Together:

example + .com

forms the domain name:

example.com

---

7️⃣ Subdomains

A domain can have subdomains.

For example:

blog.example.com

Here:

blog.example.com
│    │       │
│    │       └── TLD
│    └────────── Domain
└─────────────── Subdomain

Common examples include:

www.example.com
blog.example.com
shop.example.com
mail.example.com
api.example.com

Different subdomains can be used for different services.

For example:

example.com
      │
      ├── www.example.com
      ├── blog.example.com
      ├── shop.example.com
      └── api.example.com

---

8️⃣ Domain Name and Website

A domain name does not automatically mean there is a website behind it.

A domain can be used for different purposes, including:

- Websites
- Email
- APIs
- Applications
- Other Internet services

For example:

example.com

could point to a web server.

While:

mail.example.com

could point to a mail service.

---

9️⃣ Domain Registration

Before using a domain name, it generally needs to be registered through a domain registrar.

Examples of registrars include companies that allow people and organizations to register domain names.

The registration process can look like:

Choose Domain
     ↓
Check Availability
     ↓
Register Domain
     ↓
Configure DNS
     ↓
Connect Domain to Service

Domain registration does not necessarily mean that the website itself is hosted by the same company.

The domain and hosting can be managed separately.

---

🔟 Domain Registrar vs Web Host

This is an important distinction.

Domain Registrar

Provides domain registration services.

Registrar
    ↓
Domain Name

Web Host

Provides infrastructure where website files or applications can run.

Web Host
    ↓
Server
    ↓
Website/Application

They can be the same company, but they don't have to be.

For example:

Domain Registrar
      │
      │ example.com
      ▼
     DNS
      │
      ▼
Different Web Host
      │
      ▼
    Website

---

1️⃣1️⃣ What Happens When I Type a Domain?

Suppose I type:

https://example.com

into my browser.

A simplified process is:

1. I enter example.com
          ↓
2. Browser needs the IP address
          ↓
3. DNS lookup occurs
          ↓
4. DNS provides an IP address
          ↓
5. Browser connects to the server
          ↓
6. Browser sends an HTTP/HTTPS request
          ↓
7. Server responds
          ↓
8. Browser displays the website

This connects the topics I have already learned:

Domain Names
      ↓
DNS
      ↓
IP Address
      ↓
Server
      ↓
HTTP/HTTPS
      ↓
Browser
      ↓
Website

---

1️⃣2️⃣ Domain Names and DNS

A domain name is closely connected to DNS.

DNS stands for:

Domain Name System

DNS translates names into information that computers can use to locate services.

For example:

example.com
     ↓
    DNS
     ↓
IP Address
     ↓
Web Server

DNS is much more than simply converting domain names to IP addresses, and I will study it in greater detail in the next topic.

---

1️⃣3️⃣ DNS Records

Domains can have different types of DNS records.

Some important records include:

Record| Purpose
A| Maps a domain to an IPv4 address
AAAA| Maps a domain to an IPv6 address
CNAME| Creates an alias for another domain name
MX| Specifies mail servers
TXT| Stores text information, often used for verification and email-related configurations
NS| Identifies authoritative name servers

For example:

example.com
     │
     ├── A      → IPv4 address
     ├── AAAA   → IPv6 address
     ├── MX     → Mail server
     └── TXT    → Verification information

I will explore these records more deeply when I study DNS.

---

1️⃣4️⃣ Domain Name Example

Imagine I create a website for my IT business.

I might register:

mukhtaartech.com

I could then create subdomains:

mukhtaartech.com
│
├── www.mukhtaartech.com
├── support.mukhtaartech.com
├── portal.mukhtaartech.com
└── api.mukhtaartech.com

Each could potentially be configured for a different purpose.

For example:

portal.mukhtaartech.com
        ↓
Customer Portal

support.mukhtaartech.com
        ↓
Support System

api.mukhtaartech.com
        ↓
Backend API

This is an example of how domain names can become part of a larger web application architecture.

---

1️⃣5️⃣ Domain Names Are Hierarchical

Domain names have a hierarchical structure.

For example:

www.example.com

can be viewed as:

              .
              │
             com
              │
           example
              │
             www

At the top is the DNS root.

Below the root are top-level domains such as:

.com
.org
.net
.ke

Below the TLD is the domain.

Below the domain can be subdomains.

---

1️⃣6️⃣ Domain Names Are Not the Same as URLs

These terms are related but different.

Domain

example.com

URL

https://example.com/about/contact

The URL contains more information.

A simplified URL:

https://example.com/about
│       │           │
│       │           └── Path
│       └────────────── Domain
└────────────────────── Protocol

So:

Domain = example.com

while:

URL = https://example.com/about

---

🧠 Putting Everything Together

The relationship between the concepts I have learned so far can be represented as:

                    USER
                      │
                      ▼
                  BROWSER
                      │
                      │ URL
                      ▼
                DOMAIN NAME
                      │
                      ▼
                     DNS
                      │
                      │ IP Address
                      ▼
                   SERVER
                      │
                      │ HTTP/HTTPS
                      ▼
                  RESPONSE
                      │
                      ▼
                  BROWSER
                      │
                      ▼
                 WEB PAGE

---

📝 What I Learned

From this topic, I learned that a domain name is a human-friendly way of identifying an Internet destination or service.

I learned that:

- Domain names are easier for humans to remember than IP addresses.
- DNS helps connect domain names with network information.
- A domain name is different from a URL.
- Domains can have subdomains.
- Domain registration and web hosting are separate concepts.
- DNS records can provide different types of information.
- Domains can be used for websites, email, APIs, and other services.
- A domain does not automatically mean that the website is hosted by the domain registrar.

---

💡 Key Terms

Term| Meaning
Domain Name| Human-readable name used to identify an Internet service or destination
TLD| Top-Level Domain such as ".com" or ".ke"
Subdomain| A domain created under another domain
Registrar| Company/service through which domain names can be registered
DNS| System that helps resolve domain names and other DNS information
IP Address| Network address used to identify a destination
URL| Complete address used to locate a resource
DNS Record| Information stored in DNS for a domain
A Record| DNS record for an IPv4 address
AAAA Record| DNS record for an IPv6 address
CNAME| DNS alias pointing to another domain name
MX Record| Specifies mail servers
NS Record| Identifies authoritative name servers

---

❓ Questions I Want to Explore Next

- How does DNS actually work?
- What happens during a DNS lookup?
- What is a DNS resolver?
- What are root name servers?
- What are TLD name servers?
- What are authoritative name servers?
- How does DNS caching work?
- What is DNS propagation?
- How do I configure DNS records for my own domain?

---

📈 Progress

Stage: Web Fundamentals

Topic: Domain Names

Status: 🟡 Learning

Previous: "Web Browsers" (../03-web-browsers/)

Next: DNS

---

«Domain names give the Internet human-friendly names, while DNS helps turn those names into information computers can use.»
