```mermaid
sequenceDiagram
    participant User as Usuario
    participant Browser as Navegador
    participant Server as Servidor

    User->>Browser: Escribe una nota en el campo de texto
    User->>Browser: Hace clic en el botón "Save"
    Browser->>Server: Envia una solicitud HTTP POST con la nueva nota al endpoint /new_note
    Server-->>Browser: Responde con un redireccionamiento (HTTP 302) a /
    Browser->>Server: Solicita nuevamente la página principal (GET /)
    Server-->>Browser: Responde con el HTML actualizado
    Browser->>Server: Solicita los datos JSON con todas las notas (GET /data.json)
    Server-->>Browser: Envía el JSON con las notas actualizadas
    Browser->>User: Muestra la nueva nota en la lista