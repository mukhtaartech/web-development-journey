# 🌐 05 — DNS (Domain Name System)

## 📖 Introduction

In the previous topic, I learned about **domain names** and how they provide human-friendly names for Internet services.

The next question is:

> **How does a computer turn a domain name like `example.com` into information it can use to reach the correct server?**

The answer involves **DNS — the Domain Name System**.

DNS is one of the fundamental systems that makes the Internet easier to use.

Without DNS, users would often need to remember IP addresses instead of domain names.

---

# 1️⃣ What Is DNS?

**DNS** stands for:

> **Domain Name System**

DNS is a distributed naming system used to translate domain names into information such as IP addresses.

For example:

```text
example.com
     ↓
    DNS
     ↓
93.184.216.34
```

The browser can then use the resulting network information to communicate with the appropriate server.

A simplified idea is:

```text
Human
  ↓
Domain Name
  ↓
DNS
  ↓
IP Address
  ↓
Server
```

---

# 2️⃣ Why Do We Need DNS?

Computers communicate across networks using addresses such as IP addresses.

For example:

```text
93.184.216.34
```

But remembering IP addresses for every website would be difficult.

Imagine trying to remember:

```text
Website A → 192.0.2.10
Website B → 192.0.2.20
Website C → 192.0.2.30
Website D → 192.0.2.40
```

Instead, we can use:

```text
website-a.com
website-b.com
website-c.com
website-d.com
```

DNS provides the system that allows these human-readable names to be resolved.

---

# 3️⃣ DNS Is Like an Internet Directory

A simple way I understand DNS is to think of it as a **directory for Internet names**.

If I know:

```text
example.com
```

DNS helps me find the information associated with that name.

Similar to looking up someone's name in a contact list:

```text
Name
 ↓
Contact Information
```

DNS can be thought of as:

```text
Domain Name
 ↓
DNS Information
 ↓
IP Address / Other Records
```

However, DNS is much more powerful than a simple phonebook because it is a distributed system containing different types of records and servers.

---

# 4️⃣ DNS and the Web Browser

When I enter:

```text
https://example.com
```

into a browser, the browser needs to determine where to send the request.

A simplified process is:

```text
Browser
   │
   │ "What is the IP address for example.com?"
   ▼
DNS Resolver
   │
   ▼
DNS System
   │
   ▼
IP Address
   │
   ▼
Browser
```

The browser can then continue connecting to the server.

---

# 5️⃣ What Is a DNS Resolver?

A **DNS resolver** is responsible for finding the DNS information requested by a client.

A client usually does not directly communicate with every DNS server involved in the process.

Instead, it commonly sends a query to a **recursive DNS resolver**.

For example:

```text
Browser
   ↓
Operating System
   ↓
DNS Resolver
   ↓
DNS Hierarchy
```

The resolver does the work of finding the answer and returning it to the client.

---

# 6️⃣ Recursive DNS Resolver

A recursive resolver receives a DNS query and attempts to obtain the requested answer.

For example:

```text
Client
  │
  │ "Find example.com"
  ▼
Recursive Resolver
  │
  │ Searches DNS
  ▼
Answer
  │
  ▼
Client
```

The resolver may already have the answer in its cache.

If it does not, it may need to query other DNS servers.

---

# 7️⃣ DNS Caching

DNS queries are often cached.

Caching means temporarily storing information so it can be reused later.

For example:

```text
First Request

Client
  ↓
Resolver
  ↓
DNS lookup
  ↓
IP Address

Second Request

Client
  ↓
Resolver
  ↓
Cached Answer
  ↓
IP Address
```

Caching can reduce:

* Lookup time
* Network traffic
* DNS server workload

---

# 8️⃣ TTL — Time To Live

DNS records can have a **TTL**, or Time To Live.

TTL tells DNS systems how long a record can be cached before it should be considered expired and queried again.

For example:

```text
DNS Record
TTL = 3600 seconds
```

This means the record can generally be cached for:

```text
3600 seconds
= 1 hour
```

TTL values depend on how the domain's DNS is configured.

---

# 9️⃣ The DNS Hierarchy

DNS is organized hierarchically.

A simplified structure is:

```text
                    Root
                     │
          ┌──────────┼──────────┐
          │          │          │
         .com       .org       .ke
          │          │          │
          ▼          ▼          ▼
       example    example    example
          │
          ▼
       Subdomain
```

The major levels include:

1. Root
2. Top-Level Domain (TLD)
3. Authoritative domain servers

---

# 🔟 Root DNS Servers

At the top of the DNS hierarchy is the **DNS root**.

The root system directs queries toward the appropriate TLD name servers.

For example, if the query concerns:

```text
example.com
```

the root system helps direct the resolver toward the `.com` TLD infrastructure.

The root does not normally provide the final IP address for every website.

Instead, it helps guide the query.

---

# 1️⃣1️⃣ TLD Name Servers

TLD stands for:

**Top-Level Domain**

Examples include:

```text
.com
.org
.net
.ke
.uk
.id
```

TLD name servers know which authoritative name servers are responsible for domains within their TLD.

For example:

```text
example.com
     │
     ▼
Root
     │
     ▼
.com TLD
     │
     ▼
Authoritative DNS
```

---

# 1️⃣2️⃣ Authoritative DNS Servers

An **authoritative DNS server** contains the authoritative DNS records for a domain.

For example:

```text
example.com
     │
     ▼
Authoritative DNS Server
     │
     ├── A Record
     ├── AAAA Record
     ├── MX Record
     ├── TXT Record
     └── CNAME Record
```

The authoritative server is ultimately responsible for providing the DNS information for that domain.

---

# 1️⃣3️⃣ How a DNS Lookup Works

Let's look at a simplified example.

I enter:

```text
example.com
```

into my browser.

The process may look like:

```text
                Browser
                   │
                   ▼
            DNS Resolver
                   │
                   ▼
                 Root
                   │
                   ▼
              .com TLD
                   │
                   ▼
        Authoritative DNS
                   │
                   ▼
             IP Address
                   │
                   ▼
                Browser
```

The resolver then returns the answer to the client.

---

# 1️⃣4️⃣ Recursive vs Iterative Queries

There are two concepts I need to understand.

### Recursive Query

The client asks the resolver to find the answer.

```text
Client
  │
  │ "Find the answer for me."
  ▼
Resolver
```

The resolver does the work.

### Iterative Process

The resolver may ask DNS servers for directions.

For example:

```text
Resolver
   ↓
Root
   ↓
.com TLD
   ↓
Authoritative Server
```

Each server can provide information that helps the resolver continue.

---

# 1️⃣5️⃣ DNS Records

DNS contains different types of records.

Some important ones are:

| Record | Purpose                                 |
| ------ | --------------------------------------- |
| A      | Maps a name to an IPv4 address          |
| AAAA   | Maps a name to an IPv6 address          |
| CNAME  | Creates an alias to another domain name |
| MX     | Specifies mail servers                  |
| NS     | Identifies authoritative name servers   |
| TXT    | Stores text information                 |
| PTR    | Used for reverse DNS lookups            |
| SOA    | Contains information about a DNS zone   |

---

# 1️⃣6️⃣ A Record

An **A record** maps a domain name to an IPv4 address.

Example:

```text
example.com
     ↓
A
     ↓
192.0.2.10
```

Conceptually:

```text
example.com → 192.0.2.10
```

---

# 1️⃣7️⃣ AAAA Record

An **AAAA record** is used to map a domain name to an IPv6 address.

Example:

```text
example.com
     ↓
AAAA
     ↓
2001:db8::10
```

The difference is:

```text
A     → IPv4
AAAA  → IPv6
```

---

# 1️⃣8️⃣ CNAME Record

A **CNAME** record creates an alias from one domain name to another domain name.

For example:

```text
www.example.com
       ↓
CNAME
       ↓
example.com
```

This means `www.example.com` can be configured as an alias for `example.com`.

---

# 1️⃣9️⃣ MX Record

An **MX record** specifies the mail servers responsible for receiving email for a domain.

For example:

```text
example.com
     ↓
MX
     ↓
mail.example.com
```

This is important when setting up email services for a domain.

---

# 2️⃣0️⃣ NS Record

An **NS record** identifies the name servers that are authoritative for a DNS zone.

For example:

```text
example.com
     ↓
NS
     ↓
ns1.example-dns.com
ns2.example-dns.com
```

These servers can contain the authoritative DNS records for the domain.

---

# 2️⃣1️⃣ TXT Record

A **TXT record** stores text information associated with a domain.

TXT records are commonly used for things such as:

* Domain verification
* Email authentication
* SPF information
* Other service configurations

For example:

```text
example.com
     ↓
TXT
     ↓
"verification=value"
```

---

# 2️⃣2️⃣ Reverse DNS

Normal DNS usually works like:

```text
Domain
  ↓
IP Address
```

Reverse DNS works in the opposite direction:

```text
IP Address
  ↓
Domain Name
```

This commonly involves a **PTR record**.

For example:

```text
192.0.2.10
     ↓
PTR
     ↓
example.com
```

Reverse DNS is useful for various networking and email-related purposes.

---

# 2️⃣3️⃣ DNS and Networking

DNS is not only important for web development.

It is also a fundamental networking service.

For example, on a network:

```text
Computer
   │
   │ DNS Query
   ▼
DNS Server
   │
   │ Answer
   ▼
Computer
```

This is something I can encounter when working with:

* Routers
* DHCP
* Servers
* Firewalls
* Active Directory
* Network troubleshooting
* Internet services

---

# 2️⃣4️⃣ DNS Troubleshooting

DNS problems can cause websites and services to become unreachable even when the server itself is working.

For example:

```text
User
  ↓
Website
  X
DNS Resolution Failed
```

Some useful commands for investigating DNS include:

### Windows

```text
nslookup example.com
```

### Linux

```text
dig example.com
```

or:

```text
nslookup example.com
```

These tools can show information about DNS resolution.

---

# 2️⃣5️⃣ DNS Example

Imagine I create:

```text
mukhtaartech.com
```

I want the website to point to my web server.

I could configure an A record such as:

```text
mukhtaartech.com
      ↓
A
      ↓
[Web Server IPv4 Address]
```

Then I might create:

```text
www.mukhtaartech.com
```

as an alias:

```text
www.mukhtaartech.com
          ↓
       CNAME
          ↓
mukhtaartech.com
```

For email, I could have:

```text
mukhtaartech.com
      ↓
     MX
      ↓
Mail Server
```

This demonstrates how one domain can use different DNS records for different services.

---

# 🧠 Complete DNS Journey

Putting everything together:

```text
                    USER
                      │
                      ▼
                  BROWSER
                      │
                      │ Domain
                      ▼
              DNS RESOLVER
                      │
                      │ Query
                      ▼
                    ROOT
                      │
                      │ Referral
                      ▼
                  TLD SERVER
                      │
                      │ Referral
                      ▼
             AUTHORITATIVE DNS
                      │
                      │ DNS Record
                      ▼
                 IP ADDRESS
                      │
                      ▼
                  BROWSER
                      │
                      │ HTTP/HTTPS
                      ▼
                   SERVER
                      │
                      ▼
                 WEB PAGE
```

---

# 📝 What I Learned

From this topic, I learned that DNS is a distributed system that allows humans to use domain names while computers and network services can use information such as IP addresses.

I learned that:

* DNS stands for Domain Name System.
* DNS is hierarchical.
* DNS resolvers help clients find DNS information.
* DNS information can be cached.
* TTL controls how long DNS information can generally remain cached.
* Root DNS helps direct queries toward TLD infrastructure.
* TLD servers help identify authoritative DNS servers.
* Authoritative DNS servers provide the actual DNS records for a domain.
* Different DNS records serve different purposes.
* DNS is important for both web development and networking.
* DNS troubleshooting is an important networking skill.

---

# 💡 Key Terms

| Term               | Meaning                                                         |
| ------------------ | --------------------------------------------------------------- |
| DNS                | Domain Name System                                              |
| DNS Resolver       | System that finds DNS information for clients                   |
| Recursive Resolver | Resolver that performs the lookup process on behalf of a client |
| Root               | Top level of the DNS hierarchy                                  |
| TLD                | Top-Level Domain                                                |
| Authoritative DNS  | DNS server responsible for a domain's authoritative records     |
| A Record           | Maps a name to an IPv4 address                                  |
| AAAA Record        | Maps a name to an IPv6 address                                  |
| CNAME              | Alias for another domain name                                   |
| MX                 | Specifies mail servers                                          |
| NS                 | Identifies authoritative name servers                           |
| TXT                | Stores text information                                         |
| PTR                | Used for reverse DNS                                            |
| TTL                | Time To Live; controls DNS caching duration                     |

---

# 🧪 Practical Experiment

I want to test DNS resolution myself.

### Windows

Open Command Prompt and run:

```text
nslookup google.com
```

Then try:

```text
nslookup github.com
```

I can observe:

* The DNS server being used
* The domain being queried
* The IP addresses returned

I can also try:

```text
nslookup -type=MX google.com
```

to investigate mail-related DNS records.

---

# ❓ Questions I Want to Explore Next

* What exactly happens during DNS propagation?
* Why can DNS changes take time to appear?
* What is DNS caching at different levels?
* What is a DNS zone?
* What is a nameserver?
* What is the difference between a DNS resolver and a nameserver?
* How does DNS over HTTPS work?
* How does DNS over TLS work?
* How can I configure DNS for my own domain?

---

## 📈 Progress

**Stage:** Web Fundamentals

**Topic:** DNS (Domain Name System)

**Status:** 🟡 Learning

**Previous:** [Domain Names](../04-domain-names/)

**Next:** Web Hosting

---

> **DNS is one of the systems that turns human-friendly names into information that allows Internet services to be found.**
