# PROTOCOLO DE AUDITORÍA Y APROBACIÓN DE ENTREGABLES
## Ecosistema Digital CIASA RD

---

### 1. Flujo de Trabajo y Pase de Etapas

```mermaid
flowchart TD
    A[1. Desarrollo Local en CIASARD-produccion] --> B[2. Pruebas Locales en localhost:3000]
    B --> C[3. Despliegue a Staging Hostinger]
    C --> D[4. Auditoría Técnica Interna por Nuestro Equipo]
    D -->|¿Hay observaciones?| A
    D -->|Aprobado Internamente| E[5. Sesión de Demostración con Paola Caram / CIASA]
    E -->|Ajustes Solicitados| A
    E -->|Conforme| F[6. Firma de Acta de Entrega & Sign-off]
    F --> G[7. Activación Oficial de la Siguiente Fase]
```

---

### 2. Niveles de Validación Técnica
1. **Nivel 1 — Código y Servidor (Node.js / Express):**
   - Cero errores de sintaxis o dependencias faltantes.
   - Clean URLs canónicas sin extensiones `.html`.
   - Streaming HTTP 206 operativo para videos MP4.
   - Cabeceras de seguridad activas.
2. **Nivel 2 — Interfaz y Experiencia de Usuario (UI/UX):**
   - Adaptabilidad 100% responsiva (Móvil, Tablet, Desktop).
   - Sin emojis (solo iconos SVG y tipografía ejecutiva).
   - Formularios y botones de WhatsApp vinculados correctamente.
3. **Nivel 3 — Módulo Administrativo y CRM:**
   - Acceso seguro a `/admin/login`.
   - Creación y edición de propiedades, leads y artículos.
   - Exportación de prospectos NPI en lotes de 150 leads.
4. **Nivel 4 — Aprobación del Cliente:**
   - Verificación en vivo por parte de la Directora Comercial.
   - Firma del Acta de Entrega.
