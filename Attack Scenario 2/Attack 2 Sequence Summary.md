# Summary MITRE ATT&CK Sequence

# Attack Description

The attacker, an Advanced Persistent Threat (APT) group, initiates the Distributed Denial of Service (DDoS) attack by leveraging a network of compromised devices to overwhelm TaskHub’s servers with a massive influx of traffic. The goal is to exhaust system resources and disrupt normal operations, rendering the service inaccessible to legitimate users. By orchestrating the attack through a large-scale botnet, the attacker can effectively bypass individual security measures and create widespread service disruption.

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

    Reconnaissance[Reconnaissance] -->|Identify TaskHub's network infrastructure and vulnerabilities| Weaponization[Weaponization]
    Weaponization -->|Assemble a botnet of compromised devices| Delivery[Delivery]
    Delivery -->|Launch a massive flood of traffic to TaskHub’s servers| Exploitation[Exploitation]
    Exploitation -->|Overwhelm TaskHub’s resources and disrupt service| Installation[Installation]
    Installation -->|Monitor the attack's impact and adjust strategy if needed| Command_Control[Command and Control]
    Command_Control -->|Communicate with the botnet and manage the attack| Actions_Objectives[Actions on Objectives]
    Actions_Objectives -->|Maintain service disruption for as long as possible| Actions_Objectives

    subgraph MITRE_Attack[MITRE ATT&CK Techniques]
    style MITRE fill:#85C1E9,stroke:#000,stroke-width:2px
    Delivery -->|T1203 - Exploitation for Client Execution| MITRE
    Exploitation -->|T1499 - Endpoint Denial of Service| MITRE
    Command_Control -->|T1071.001 - Application Layer Protocol| MITRE
    end


