sequenceDiagram
    participant browser
    participant server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa
    activate server
    browser-->>server: Documento HTML
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: Documento CSS llamado main.css
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js
    activate server
    server-->>browser: Documento JavaScript llamado spa.js
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{content: "dwada", date: "2024-08-13T16:35:11.626Z"},…]
    deactivate server

    browser-->>: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    activate server
    server-->>browser: [{content: "otra nota", date: "2024-08-13T23:45:39.972Z"}]
    desactivate server
Note right of browser: Si bien yo puse todo de vuelta, lo importante seria lo ultimo, los datos JSON llamados new_note_spa ya que cuando se manda una nota solo se cargan el archivo JSON en