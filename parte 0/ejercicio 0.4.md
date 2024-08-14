sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes
    activate server
    browser-->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    server-->browser: Documento HTML
    deactivate server
Note right of browser: Se pide una nueva solicitud HTTP GET ya que el código de estado es HTTP 302.
Note right of browser: La nueva nota es "buenas"

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Documento CSS llamado main.css
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: Documento JavaScript llamado main.js
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser:  [{content: "rww", date: "2024-08-13T15:35:42.672Z"}, {,…}, {,…},…]
    deactivate server
