# Exercise 0.5

Create a diagram depicting the situation where the user goes to the single-page app version of the notes app at https://studies.cs.helsinki.fi/exampleapp/spa.

## Diagram

```mermaid

sequenceDiagram
participant Browser
participant Server

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/spa
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
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/spa.js
deactivate Browser
activate Server
Server->>Browser: Javascript file, status code 200
deactivate Server

Note right of Browser: browser runs code to fetch json data  

activate Browser
Browser->>Server: GET request to https://studies.cs.helsinki.fi/exampleapp/data.json
deactivate Browser
activate Server
Server->>Browser: Json file, status code 200
deactivate Server

Note right of Browser: browser invokes the callback function that renders notes on page

```

