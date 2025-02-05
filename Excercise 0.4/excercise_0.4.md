# Excercise 0.4

Create a diagram depicting the situation where the user creates a new note on the page <https://studies.cs.helsinki.fi/exampleapp/notes> by writing something into the text field and clicking the Save button.

If necessary, show operations on the browser or on the server as comments on the diagram.

## Diagram

```mermaid

sequenceDiagram
participant Browser
participant Server

activate Browser
Browser ->>Server: form submit sends a POST request to server address https://studies.cs.helsinki.fi/exampleapp/new_note
deactivate Browser
activate Server
Server ->>Browser: redirect to address in header's location property, status code 302
deactivate Server

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/notes
deactivate Browser
activate Server
Server->>Browser: HTML document, status code 200
deactivate Server

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/main.css
deactivate Browser
activate Server
Server->>Browser: CSS file, status code 200
deactivate Server

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/main.js
deactivate Browser
activate Server
Server->>Browser: Javascript file, status code 200
deactivate Server

Note left of Browser: Browser fetches the json data after script loads

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/data.json
deactivate Browser
activate Server
Server->>Browser: Json file, status code 200
deactivate Server

Note left of Browser: Browser invokes the callback function to render the notes from json data

```
