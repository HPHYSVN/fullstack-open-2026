sequenceDiagram
    participant U as User 
    participant B as Browser
    participant S as Server

    U->>B: Navigate to /spa
    activate B
    B->>S: GET /spa
    S-->>B: HTML (include script tag for spa.js)
    B->>S: GET /spa.js
    S-->>B: JavaScript (spa.js)
     
    Note over B: Browser executes spa.js
    activate B
    B->>S: GET /data.json
    S-->>B: JSON data (list of notes)
    
    Note over B: DOM API creates list elements<br/>and renders notes to screen
    deactivate B
    B-->>U: Display full notes page
    deactivate B