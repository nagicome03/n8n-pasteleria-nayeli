# Pastelería La Cuchara: automatizaciones con n8n

- La app (http://pasteleria:8000 dentro de Docker) guarda encargos y pagos. Se usa por API con la cabecera X-API-Key (credencial "API Pastelería" en n8n).
- n8n corre en Docker. Los correos salen por la credencial SMTP "Mailpit".
- Los flujos se guardan como JSON en `mis-flujos/` con el formato `NN-nombre.json`.
- Los importes siempre los calcula la app: n8n solo los muestra.
- NO escribir credenciales ni claves dentro de los JSON. NO publicar flujos sin que yo los haya probado.