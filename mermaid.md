```mermaid
graph TD;
    A[Start Camera]
    B[Use Gaze Tracking to Detect Gaze]
    C{gaze.is_blinking > 2 seconds?}
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
    B --> E
    B --> G
    C -- Yes --> D
    C -- No --> B
    D --> I
    E -- Yes --> F
    E -- No --> B
    F --> I
    G -- Yes --> H
    G -- No --> B
    H --> I
    I -- Yes --> J
    I -- No --> B
    J --> K
    K --> L
    L -- No --> A
