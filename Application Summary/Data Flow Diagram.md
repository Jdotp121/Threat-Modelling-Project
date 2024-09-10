The Data Flow Diagram is used to highlight any key critical areas of the application that will be targeted by a likely attacker. Confirm the accuracy of the DFD with engineering teams during the workshop.


```mermaid
erDiagram
    USER ||--o{ PROJECT : "manages"
    USER ||--o{ TASK : "assigned to"
    PROJECT ||--o{ TASK : "contains"
    ORGANIZATION ||--o{ PROJECT : "owns"
    TASK ||--|{ COMMENT : "includes"
    TASK ||--o{ FILE : "has"
    FILE ||--o{ USER : "uploaded by"
    USER ||--o{ ORGANIZATION : "belongs to"
    API-INTEGRATION ||--o{ PROJECT : "integrates with"
    NOTIFICATION ||--o{ USER : "sent to"
    ROLE ||--|{ USER : "has"
