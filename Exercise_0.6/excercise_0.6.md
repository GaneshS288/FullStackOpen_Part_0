# Exercise 0.6

Create a diagram depicting the situation where the user creates a new note using the single-page version of the app.

## diagram

```mermaid

sequenceDiagram
participant Browser
participant Server

Note over Browser, Server: browser pushes new note to notes array on form submit before post request

activate Browser
Browser->>Server: POST request at https://studies.cs.helsinki.fi/exampleapp/new_note_spa
deactivate Browser
activate Server

Note left of Server: status code 201, new note created

Server->>Browser: Json file, {message : "note created"}
deactivate Server

Note right of Browser: browser invokes callback function to re render notes with local notes array


```