# AI Log

Registro de flujos generados con el agente (OpenCode).

---

## 04 · Aviso de entrega mañana — 02/11/2026

**Prompt usado:**

> Lee AGENTS.md y esta spec. Genera el flujo como un JSON importable en mis-flujos/04-aviso-entrega.json.
>
> ## Spec: aviso de entrega mañana
> - Disparador: cada día a las 9:00.
> - Pide a la API los encargos `pendiente` y `pagado` con `fecha_entrega` de mañana (GET /api/encargos).
> - Si un encargo está `pagado`: correo al cliente "Mañana puedes recoger tu tarta".
> - Si está `pendiente`: correo al cliente "Mañana es la entrega y aún te faltan X €".
> - Si hay entregas mañana, un solo correo a Marisa con la lista. Si no hay ninguna, no se envía nada.
> - Criterios de aceptación: con los datos de ejemplo, el resultado coincide con lo que dice la app; no falla si no hay entregas.

**Qué hizo bien:**

- Generó `mis-flujos/04-aviso-entrega.json` como JSON válido e importable.
- Usó las credenciales existentes por su id (`API pasteleria` y `Mailpit`), sin escribir claves.
- Los importes los toma de la app: usa `e.pendiente` tal cual lo devuelve la API, sin recalcular.
- El caso "sin entregas mañana" no envía nada (el nodo Code devuelve 0 items y los nodos de correo no ejecutan).
- Reutilizó el patrón y el estilo de los flujos anteriores (schedule, httpRequest, code, if, emailSend).

**Qué hubo que corregir:**

- Nada. Salió bien a la primera.
