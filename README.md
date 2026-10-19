# FileVault-API

To install dependencies:

```bash
bun install
```

To run:

```bash
bun run index.ts
```

## System Design
```mermaid
graph LR
    Client["Client (User/Browser)"] --> Nginx["Load Balancer (Nginx)"]
    Nginx --> Service["Service (Bun + Hono)"]
    Auth["Auth Service (Identity/OAuth)"] --> Service
    Service --> SQL["SQL Database (SQLite)"]
    Service --> Storage["Object Storage (S3/Blob)"]

    classDef client fill:#f9f,stroke:#333,stroke-width:2px,color:#000;
    classDef proxy fill:#9f9,stroke:#333,stroke-width:2px,color:#000;
    classDef api fill:#b9f,stroke:#333,stroke-width:2px,color:#000;
    classDef data fill:#fbf,stroke:#333,stroke-width:2px,color:#000;

    class Client client;
    class Nginx proxy;
    class Service,Auth api;
    class SQL,Storage data;
```

###### This project was created using `bun init` in bun v1.3.3. [Bun](https://bun.com) is a fast all-in-one JavaScript runtime.
