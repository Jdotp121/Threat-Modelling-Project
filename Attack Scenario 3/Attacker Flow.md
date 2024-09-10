  This is a an example of an attacker flow using mermaid.
  
  ```mermaid
sequenceDiagram
    participant Attacker
    participant TaskHubApp
    participant BackendServer
    participant Database

    activate Attacker
    Attacker->>TaskHubApp: Identify vulnerable input fields (e.g., login forms)
    TaskHubApp->>Attacker: Vulnerabilities identified
    deactivate Attacker

    activate Attacker
    Attacker->>TaskHubApp: Craft and submit malicious SQL query
    TaskHubApp->>BackendServer: Malicious SQL query executed
    BackendServer->>Database: Unauthorized database access granted
    deactivate Attacker

    activate Attacker
    Attacker->>Database: Exfiltrate sensitive project data
    Database->>Attacker: Sensitive data retrieved
    deactivate Attacker

    activate Attacker
    Attacker->>BackendServer: Modify or delete project tasks
    BackendServer->>Database: Project data manipulated
    deactivate Attacker


