sequenceDiagram
    participant U as User
    participant B as Browser
    participant S as Server

    U->>B: Enter note content & click "Save"
    
    activate B
    Note over B: JS Event Handler triggered<br/>calls e.preventDefault() (No reload)
    B->>B: Create note object (content + date)
    B->>S: HTTP POST /new_note_spa<br/>Body: JSON (Content-Type: application/json)
    
    S-->>B: Status 201 Created
    B->>B: Update DOM (add new note to list)
    
    B-->>U: New note visible immediately
    deactivate B
    
    Note over B,S: Only ONE HTTP request sent.<br/>No page reload occurred.sequenceDiagram


    U->>B: Enter note content & click "Save"
    
    activate B
    Note over B: JS Event Handler triggered<br/>calls e.preventDefault() (No reload)
    B->>B: Create note object (content + date)
    B->>S: HTTP POST /new_note_spa<br/>Body: JSON (Content-Type: application/json)
    
    S-->>B: Status 201 Created
    B->>B: Update DOM (add new note to list)
    
    B-->>U: New note visible immediately
    deactivate B
    
    Note over B,S: Only ONE HTTP request sent.<br/>No page reload occurred.sequenceDiagram


    U->>B: Enter note content & click "Save"
    
    activate B
    Note over B: JS Event Handler triggered<br/>calls e.preventDefault() (No reload)
    B->>B: Create note object (content + date)
    B->>S: HTTP POST /new_note_spa<br/>Body: JSON (Content-Type: application/json)
    
    S-->>B: Status 201 Created
    B->>B: Update DOM (add new note to list)
    
    B-->>U: New note visible immediately
    deactivate B
    
    Note over B,S: Only ONE HTTP request sent.<br/>No page reload occurred.