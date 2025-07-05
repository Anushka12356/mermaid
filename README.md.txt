# SAS Holdings – Production Line Automation Flowchart

```mermaid
flowchart TD
    A[Start] --> B[Display Company Info, Logo, Date, Time]
    B --> C{Is Login Correct?}
    C -- Yes --> D[Show Menu]
    C -- No --> E[Increase Attempt Count]
    E --> F{Attempts > 3?}
    F -- Yes --> Z[Exit]
    F -- No --> C

    D --> G{User Choice?}
    G -- Line Details --> H[Show Line Details]
    H --> I{Continue?}
    G -- Item Request --> J[Input: Item Name, Machine Count, Per Machine Req]
    J --> K[Calculate Total Requirement]
    K --> I
    G -- Logout --> Z

    I -- Yes --> D
    I -- No --> Z