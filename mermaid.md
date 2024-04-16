```mermaid
graph TD;
    A[Start Camera]
    B[Gaze Tracking Recognition]
    C{Gaze.is_blinking() > 2s?}
    D[Issue Warning for Drowsiness]
    E{Pupil Y-axis Change > 10?}
    F[Issue Warning for Phone Usage]
    G{Face Not Detected?}
    H[Issue Warning for Side Glance]
    I{Warning Count > 3?}
    J[Activate Emergency Blinkers]
    K[Continue Gaze Tracking]
    L[Stop Gaze Tracking on Stop]

    A --> B
    B --> C
    C -- Yes --> D
    C -- No --> E
    D --> I
    E -- Yes --> F
    E -- No --> G
    F --> I
    G -- Yes --> H
    G -- No --> K
    H --> I
    I -- Yes --> J
    I -- No --> K
    J --> K
    K --> B
    K --> L
