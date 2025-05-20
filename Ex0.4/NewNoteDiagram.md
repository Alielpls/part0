```mermaid
sequenceDiagram
 participant browser
    participant server

        Note right of browser: This is after the user types the text and press the save button
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
        Note right of browser: As it is a POST request, the content is in the request body
    server-->>browser: HTTP Status code 302
    deactivate server
        Note right of browser: After the server response, the page is redirected to the route "/notes"

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server


    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{ "content": "Oasis is back", "date": "2025-05-20" }, ... ]
    deactivate server
```
