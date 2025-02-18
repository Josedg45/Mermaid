```mermaid
graph TD;
    A[User types text in the input field] --> B[User clicks the 'Save' button];
    
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




```mermaid
graph TD;
    A[User navigates to the SPA page] --> B[Browser requests HTML from server];
    B -->|GET /spa| C[Server responds with HTML];

    C --> D[Browser parses HTML and requests CSS & JavaScript];
    D -->|GET /main.css| E[Server sends CSS file];
    D -->|GET /spa.js| F[Server sends JavaScript file];

    F --> G[JavaScript executes in the browser];
    G --> H[JavaScript sends GET request for existing notes];

    H -->|GET /data.json| I[Server responds with saved notes in JSON format];
    I --> J[JavaScript processes JSON and updates the UI];

    J --> K[User sees the list of notes and can interact];

    %% Grouping browser and server operations
    subgraph "Operations in the Browser"
        A;
        C;
        D;
        G;
        H;
        J;
        K;
    end

    subgraph "Operations in the Server"
        B;
        E;
        F;
        I;
    end
