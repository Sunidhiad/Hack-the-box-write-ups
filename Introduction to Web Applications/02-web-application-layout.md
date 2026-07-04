#  Web Application Layout

---

# Objective

Understand how web applications are structured, the different infrastructure models they use, the core components involved, and how architecture impacts both scalability and security.

---

# Web Application Layout

A web application's layout can be divided into three main areas.

| Category | Description |
|----------|-------------|
| Web Application Infrastructure | Physical deployment of servers, databases, and services. |
| Web Application Components | Client, server, database, APIs, and other application services. |
| Web Application Architecture | How all components communicate and work together. |

---

# Web Application Infrastructure Models

## Client-Server Model

The client-server model is the foundation of most web applications.

- Client (Browser) sends HTTP requests.
- Server processes the request.
- Server returns an HTTP response.

Basic workflow:

```
Browser
    │
HTTP Request
    │
    ▼
Web Server
    │
Processes Request
    │
HTTP Response
    ▼
Browser
```

---

## One Server Architecture

All components are hosted on a single server.

Includes:

- Web Server
- Application
- Database

### Advantages

- Easy to deploy
- Simple configuration

### Disadvantages

- Single point of failure
- Poor scalability
- If compromised, all applications and data may be exposed

---

## Many Servers – One Database

Multiple application servers share one central database.

```
Clients
    │
Multiple Web Servers
        │
Shared Database
```

### Advantages

- Better scalability
- Improved availability
- Web servers remain independent

### Disadvantages

- Database becomes a critical component
- Requires proper access control

---

## Many Servers – Many Databases

Each application has its own database.

```
Web Server A → Database A

Web Server B → Database B

Web Server C → Database C
```

### Advantages

- Better isolation
- Improved security
- Easier redundancy
- High availability

This is one of the most secure and scalable deployment models.

---

# Web Application Components

A modern web application commonly consists of the following components.

| Component | Purpose |
|----------|---------|
| Client | User's browser |
| Web Server | Handles HTTP requests |
| Application Logic | Processes business logic |
| Database | Stores application data |
| APIs | Exchange data with other applications |
| Microservices | Independent application services |
| Third-Party Integrations | External services such as payment gateways |
| Serverless Functions | Cloud-based event-driven functions |

---

# Three-Tier Architecture

Most web applications follow a Three-Tier Architecture.

| Layer | Description |
|-------|-------------|
| Presentation Layer | User Interface (HTML, CSS, JavaScript) |
| Application Layer | Business logic, authentication, authorization |
| Data Layer | Databases and data storage |

Workflow:

```
Presentation Layer
        │
Application Layer
        │
Data Layer
```

---

# Microservices

Microservices divide an application into small independent services.

Example:

- Registration
- Search
- Payments
- Reviews
- Ratings

Each service performs a single task and communicates with the others through APIs.

### Benefits

- Easier scaling
- Faster development
- Independent deployment
- Better fault isolation
- Reusable code

---

# Serverless Architecture

Cloud providers such as:

- AWS
- Microsoft Azure
- Google Cloud Platform (GCP)

allow applications to run without managing servers directly.

Instead, developers deploy functions that execute only when triggered.

### Benefits

- No server management
- Automatic scaling
- Lower operational costs
- Faster deployment

---

# Architecture Security

Security is not only about writing secure code—it also depends on application design.

Poor architecture can introduce serious vulnerabilities even when the code itself is secure.

Examples include:

- Missing Role-Based Access Control (RBAC)
- Excessive user privileges
- Improper network segmentation
- Shared databases without proper permissions
- Weak communication between services

Good architecture reduces the overall attack surface.

---

# Infrastructure Comparison

| Model | Scalability | Security | Availability |
|--------|------------|----------|--------------|
| One Server | Low | Low | Low |
| Many Servers, One Database | Medium | Medium | Medium |
| Many Servers, Many Databases | High | High | High |

---

# Key Takeaways

- Web applications can be deployed using different infrastructure models.
- The client-server model is the foundation of modern web applications.
- Three-Tier Architecture separates the presentation, application, and data layers.
- Microservices split applications into small independent services.
- Serverless computing removes the need to manage infrastructure.
- Secure architecture is as important as secure code during penetration testing.
