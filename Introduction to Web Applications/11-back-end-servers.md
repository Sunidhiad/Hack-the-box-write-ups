# Back End Servers

## 🎯 Objective

Understand the role of **Back End Servers**, their software and hardware components, common technology stacks, and how they support modern web applications.

---

# Overview

A **Back End Server** is the machine that hosts and executes all of the components required for a web application to function.

Unlike the front end, which users interact with through a browser, the back end performs all processing behind the scenes.

It:

- Processes client requests
- Executes application logic
- Communicates with databases
- Hosts web servers
- Returns responses to users

Within the **Three-Tier Architecture**, the back end belongs to the **Data Access Layer**.

---

# Main Components

A back end server typically hosts three core software components:

| Component | Purpose |
|----------|---------|
| Web Server | Receives HTTP requests and serves web content |
| Database | Stores and retrieves application data |
| Development Framework | Executes the application's business logic |

```
                Client
                   │
                   ▼
             Web Server
                   │
                   ▼
      Development Framework
                   │
                   ▼
              Database
```

---

# Additional Components

Depending on the infrastructure, a back end server may also include:

- Hypervisors
- Containers (Docker)
- Web Application Firewalls (WAF)
- Reverse Proxies
- Load Balancers
- Monitoring Services

These components improve security, scalability, and application performance.

---

# Common Web Technology Stacks

A **technology stack** is a predefined combination of operating system, web server, database, and programming language/framework.

| Stack | Components |
|-------|------------|
| LAMP | Linux + Apache + MySQL + PHP |
| WAMP | Windows + Apache + MySQL + PHP |
| WINS | Windows + IIS + .NET + SQL Server |
| MAMP | macOS + Apache + MySQL + PHP |
| XAMPP | Cross-Platform + Apache + MySQL + PHP/Perl |

---

# Popular Stack Breakdown

## LAMP

```
Linux
│
├── Apache
├── MySQL
└── PHP
```

One of the most widely used stacks for PHP applications.

Examples:

- WordPress
- Joomla
- Drupal

---

## WAMP

```
Windows
│
├── Apache
├── MySQL
└── PHP
```

Designed for Windows environments.

Often used for local web development.

---

## WINS

```
Windows
│
├── IIS
├── .NET
└── SQL Server
```

Common in enterprise Microsoft environments.

Frequently used for:

- ASP.NET applications
- Corporate web portals
- Internal business applications

---

## MAMP

```
macOS
│
├── Apache
├── MySQL
└── PHP
```

Primarily used by developers working on macOS.

---

## XAMPP

```
Cross Platform
│
├── Apache
├── MySQL
├── PHP
└── Perl
```

Runs on:

- Windows
- Linux
- macOS

Very popular for learning and testing web applications locally.

---

# Hardware

The back end server also includes the physical hardware responsible for running the application.

Typical resources include:

- CPU
- RAM
- Storage
- Network interfaces

The available hardware directly affects:

- Application speed
- Stability
- Number of concurrent users
- Overall performance

---

# Scaling Back End Servers

Large web applications rarely rely on a single server.

Instead, requests are distributed across multiple servers.

Example architecture:

```
                Users
                  │
                  ▼
           Load Balancer
          ┌──────┴──────┐
          ▼             ▼
   Web Server 1    Web Server 2
          │             │
          └──────┬──────┘
                 ▼
             Database
```

Benefits include:

- Improved availability
- Better performance
- Fault tolerance
- Easier maintenance

---

# Cloud Hosting

Modern applications often run in cloud environments rather than on dedicated physical servers.

Examples include:

- AWS
- Microsoft Azure
- Google Cloud Platform (GCP)

Cloud hosting provides:

- Virtual machines
- Auto-scaling
- Managed databases
- High availability
- Disaster recovery

---

# Security Considerations

Since the back end hosts the application's core functionality, compromising it can expose:

- Application source code
- Sensitive user data
- Databases
- Authentication systems
- Internal APIs

Common protections include:

- Firewalls
- WAFs
- Network segmentation
- Least privilege access
- Container isolation
- Regular security updates

---

# HTB Lab

## Question

What operating system is **WAMP** used with?

### Answer

```
Windows
```

---

# Key Takeaways

- The back end server executes the core functionality of a web application.
- It typically hosts the web server, database, and application framework.
- Technology stacks combine an operating system, web server, database, and programming language.
- Common stacks include LAMP, WAMP, WINS, MAMP, and XAMPP.
- Modern applications often use multiple servers and cloud infrastructure for scalability and reliability.
- Securing the back end is essential because it contains the application's most sensitive components.
