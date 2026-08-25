# FASE 2: ESPECIFICACIÓN TÉCNICA DE INTEGRACIONES
## Arquitectura de Webhooks, APIs y Conectores de Email

---

### 1. Flujo de Captura y Procesamiento de Leads

```mermaid
sequenceDiagram
    autonumber
    actor Inversionista
    participant Web as Portal Web / Wizard
    participant Node as Servidor Node.js (/api/leads)
    participant DB as MySQL Hostinger
    participant Mail as Hostinger Reach / SMTP
    participant CRM as Panel Admin CIASA

    Inversionista->>Web: Completa Formulario / Wizard
    Web->>Node: POST /api/leads (JSON Payload)
    Node->>DB: INSERT INTO leads (Nombre, Email, Tel, Presupuesto, Canal)
    Node->>Mail: Dispara Email de Confirmación con Dossier PDF
    Node->>CRM: Notificación en vivo para Paola Caram
    Mail-->>Inversionista: Recibe Ficha / Dossier en su Bandeja
```

---

### 2. Endpoints Requeridos
* `POST /api/leads/capture`: Recepción de prospectos desde el portal y páginas de detalle.
* `POST /api/leads/wizard`: Recepción del perfil inversor con cálculo de retorno estimado.
* `GET /api/sitemap.xml`: Generación dinámica del mapa de sitio para Google Search Console.
