```mermaid
sequenceDiagram
    participant User as Usuario
    participant Browser as Navegador
    participant Server as Servidor

    User->>Browser: Ingresa a https://studies.cs.helsinki.fi/exampleapp/spa
    Browser->>Server: Solicita el documento HTML (GET /spa)
    Server-->>Browser: Responde con el HTML de la SPA
    Browser->>Server: Solicita los archivos CSS y JavaScript necesarios
    Server-->>Browser: Envía los archivos CSS y JavaScript
    Browser->>Server: Solicita los datos JSON con todas las notas (GET /data.json)
    Server-->>Browser: Responde con el JSON que contiene las notas
    Browser->>User: Renderiza la SPA y muestra las notas al usuario