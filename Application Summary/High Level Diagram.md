  ```mermaid
flowchart TD
    subgraph "User Interface"
        UI[User Interface]
    end
    subgraph "Frontend (EC2)"
        FE[Frontend Server]
    end
    subgraph "Backend"
        BE[Backend Server]
    end
    subgraph "Database"
        DB[Database]
    end
    subgraph "External Services"
        Slack[Slack Integration]
        GitHub[GitHub API]
        GDrive[Google Drive Integration]
    end
    UI --> FE
    FE --> BE
    BE --> DB
    BE --> Slack
    BE --> GitHub
    BE --> GDrive
