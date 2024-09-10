This diagram maps out the flow of TaskHub, highlights common security threats, and outlines the appropriate mitigations to ensure a secure application environment using STRIDE to demonstrate the current controls in place for the application.

```mermaid      
graph TD
    subgraph User Interaction
        A[User] -->|HTTP Requests| B[Web Server]
    end

    subgraph Web Server
        B -->|Access| C[Database]
        B -->|Receive Input| D[Input Validation]
        B -->|Execute| E[Application Logic]
    end

    subgraph Database
        C -->|Store/Fetch Data| F[Data Storage]
    end

    A((User)) -.->|Authentication| G[Authentication Mechanism]

    B -.->|Logging| H[Logging Service]

    A -.->|Access| I[Admin Panel]
    I -.->|Controls| J[Admin Functionality]

    %% SQL Injection Threat
    T7([SQL Injection: Malicious Query Execution]) -.-> D
    T8([Data Exfiltration: Unauthorized Data Access]) -.-> F

    %% Other Threats
    T1([Spoofing: Spoof User Identity]) -.-> A
    T2([Tampering: Alter HTTP Request]) -.-> B
    T3([Repudiation: Deny Transactions]) -.-> H
    T4([Information Disclosure: Data Leak]) -.-> F
    T5([Denial of Service: Overload Server]) -.-> B
    T6([Elevation of Privilege: Unauthorized Access]) -.-> I

    %% SQL

