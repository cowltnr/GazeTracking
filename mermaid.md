```mermaid
graph TD;
    A[Start] --> B[Recognize Driver's Eyes]
    B --> C{Inattentive > 2 seconds?}
    C -->|Yes| D[Issue Warning Sound]
    C -->|No| B
    D --> E{Warning Sound Count > 3?}
    E -->|Yes| F[Activate Emergency Blinkers]
    E -->|No| B
