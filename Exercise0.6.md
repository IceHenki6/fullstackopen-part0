````mermaid
sequenceDiagram
  participant browser
  participant server
  
  Note right of browser: The browser sends only a POST request to the server, it uses the javascript code to send the form data, the code determines that the data type of the request to be JSON
  browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
  activate server
  Note right of browser: The server responds with a 201 created and a message that a note was created. It does not ask the browser to refresh
  server-->>browser: {"message":"note created"}
  deactivate server
  Note right of browser: The js file rerenders the notes list on the page
````
