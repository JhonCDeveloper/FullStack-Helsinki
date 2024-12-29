```mermaid
sequenceDiagram
    participant User as Usuario
    participant Browser as Navegador
    participant Server as Servidor

    User->>Browser: Escribe una nueva nota en el campo de texto
    User->>Browser: Hace clic en el botón "Save"
    Browser->>Server: Envia una solicitud HTTP POST con la nueva nota al endpoint /new_note
    Server-->>Browser: Responde con un código 201 (creado) y confirma el almacenamiento de la nota
    Browser->>Server: Solicita nuevamente los datos JSON con todas las notas (GET /data.json)
    Server-->>Browser: Envía el JSON actualizado con la nueva nota incluida
    Browser->>User: Actualiza la interfaz y muestra la nueva nota