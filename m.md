graph TD;
    A[User types text in the input field] --> B[User clicks the "Save" button];
    
    B --> C[JavaScript captures the event];
    C --> D[JavaScript sends a POST request to the server];

    D -->|POST /new_note| E[Server receives the note and saves it in the database];
    E --> F[Server responds with confirmation];

    F --> G[Browser receives the response];
    G --> H[JavaScript updates the note list on the page];

    H --> I[The new note appears in the interface];

    %% Additional Notes
    subgraph "Operations in the Browser"
        A;
        B;
        C;
        G;
        H;
        I;
    end

    subgraph "Operations in the Server"
        D;
        E;
        F;
    end


    Note right of browser: The browser executes the callback function that renders the notes

