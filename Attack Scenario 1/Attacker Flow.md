  This is a an example of an attacker flow using mermaid.
  
  ```mermaid
sequenceDiagram
    participant Attacker
    participant TaskHubApp
    participant CnCServer
    participant BackendServer
    participant User

    activate Attacker
    Attacker->>TaskHubApp: Identify TaskHub application
    TaskHubApp->>Attacker: Application identified
    deactivate Attacker

    activate Attacker
    Attacker->>TaskHubApp: Craft phishing email targeting admin users
    TaskHubApp->>Attacker: Phishing email crafted
    deactivate Attacker

    activate Attacker
    Attacker->>TaskHubApp: Deploy phishing campaign targeting users/admins
    TaskHubApp->>User: Phishing email sent
    activate User
    User->>TaskHubApp: Clicks on malicious link
    TaskHubApp->>User: Credentials harvested
    deactivate User
    deactivate Attacker

    activate Attacker
    Attacker->>TaskHubApp: Use stolen credentials to access backend
    TaskHubApp->>BackendServer: Gain access to backend using admin credentials
    BackendServer->>CnCServer: Communication established
    CnCServer->>BackendServer: Commands issued to manipulate data
    BackendServer->>CnCServer: Exfiltrate sensitive data
    deactivate Attacker

