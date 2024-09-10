# Summary MITRE ATT&CK Sequence

# Attack Description

The attacker is an Advanced Persistent Threat (APT) group that has conducted extensive research on TaskHub's architecture and potential vulnerabilities. Instead of targeting personnel or relying on phishing techniques, the attacker identifies web application input points vulnerable to SQL Injection attacks. These input fields could include login pages, search boxes, or forms where the data submitted by users is directly processed by the backend database.

The attacker initiates the attack by crafting malicious SQL queries designed to manipulate the database and bypass security controls such as authentication mechanisms. This allows the attacker to gain direct access to TaskHub's backend database, circumventing firewalls (WAF) or other security measures in place. Once inside the database, the attacker can operate with full privileges, similar to having administrative access, without needing legitimate credentials.

By exploiting this vulnerability, the attacker can view, modify, or delete sensitive project data, escalate their access to higher-level privileges, and persist in the environment for an extended period, avoiding detection.

# Methodology
The attack sequence below utilises the MITRE ATT&CK framework along with the commonly used techniques. 





```mermaid
flowchart TD
    style Reconnaissance fill:#F4D03F,stroke:#000,stroke-width:2px
    style Weaponization fill:#F5B041,stroke:#000,stroke-width:2px
    style Delivery fill:#EB984E,stroke:#000,stroke-width:2px
    style Exploitation fill:#E59866,stroke:#000,stroke-width:2px
    style Installation fill:#DC7633,stroke:#000,stroke-width:2px
    style Command_Control fill:#CA6F1E,stroke:#000,stroke-width:2px
    style Actions_Objectives fill:#BA4A00,stroke:#000,stroke-width:2px
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px

    Reconnaissance[Reconnaissance] -->|Identify vulnerable web forms or input fields| Weaponization[Weaponization]
    Weaponization -->|Craft malicious SQL query to exploit vulnerability| Delivery[Delivery]
    Delivery -->|Submit SQL injection query via web form| Exploitation[Exploitation]
    Exploitation -->|Execute unauthorized SQL commands in the backend| Installation[Installation]
    Installation -->|Gain access to TaskHub's backend database| Command_Control[Command and Control]
    Command_Control -->|Establish persistence by modifying database| Actions_Objectives[Actions on Objectives]
    Actions_Objectives -->|Exfiltrate sensitive project data| Actions_Objectives
    Actions_Objectives -->|Manipulate or delete project tasks| Actions_Objectives

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Delivery -->|T1190 - Exploit Public-Facing Application| MITRE
    Exploitation -->|T1071.001 - Application Layer Protocol| MITRE
    Exploitation -->|T1059.003 - Command and Scripting Interpreter| MITRE
    Installation -->|T1505.003 - SQL Stored Procedures| MITRE
    Command_Control -->|T1102 - Web Service| MITRE
    Command_Control -->|T1078 - Valid Accounts| MITRE
    Actions_Objectives -->|T1565.001 - Data Manipulation| MITRE
    Actions_Objectives -->|T1070 - Indicator Removal| MITRE
    end


