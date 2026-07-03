sequenceDiagram
    participant U as User 
    participant B as Browser
    participant S as Server

    U->>B: write something into form & click Save
    B->>S: POST /new_note
    activate S
    Note right of Server: Save note to array </br> Return 302 Redirect
    S-->>B: HTTP 302 (Location: /notes)
    deactivate S

    Note over B: Browser follows redirect</br> and reloads page

    B->>S: GET /notes
    activate S
    S-->>B: HTML document
    deactivate S

    B->>S: GET /main.css
    activate S
    S->>B: CSS file
    deactivate S

    B->>S: GET /main.js
    activate S
    S-->>B: JavaScript Code
    deactivate S

    B->>S: GET /data.json
    activate S
    S-->>B: JSON Data (with new note)
    deactivate S

    Note over B: Render page with new note


   