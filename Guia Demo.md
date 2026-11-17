# Guía de la demo — Capstone

## Resumen

Cada participante construye una feature completa a lo largo de los 7 labs y la presenta en 3 minutos al cierre de la clase 3. El capstone no tiene bloque propio: es el hilo que conecta todos los labs.

- **Base:** Tinybiz, el mini-ERP del workshop (Next.js 15, Drizzle ORM, SQLite), o cualquier otro proyecto que cumpla los requisitos de abajo.
- **Formato:** individual, una feature distinta por persona dentro de cada grupo (8 personas, 8 features).
- **Grupos:** Grupo A (12:00–2:30 PM) y Grupo B (3:00–5:30 PM) siguen el mismo plan.
- **Proyecto propio:** vale igual que Tinybiz. Quien lo elija es responsable de que corra y de tener su propio punto de respaldo (un tag de git por lab: `lab-m1`, `lab-m2`…).
- **Evaluación:** checklist de terminado + demo. No hay calificación numérica.

## Menú de features

Para quien elija Tinybiz. Cada feature da para 3–5 tareas en paralelo, lo mínimo para que un Agent Team de 3 agentes tenga sentido. Se asignan en la clase 1, sin repetir dentro de un grupo.

| # | Feature | Alcance mínimo | Tareas paralelizables `[P]` | Idea de MCP tool (M7) |
|---|---|---|---|---|
| 1 | Cotizaciones → venta | Crear cotización, vigencia, convertir en venta | Schema + migración · API · UI de cotización · conversión a venta | `get_open_quotes`, `convert_quote` |
| 2 | Inventario con stock mínimo | Stock por producto, umbral, alerta | Campo de umbral · cálculo de alertas · badge en UI · vista de faltantes | `get_low_stock`, `set_threshold` |
| 3 | Cuentas por cobrar | Saldo por cliente, pagos parciales | Tabla de pagos · API de abonos · estado de cuenta · UI de cobranza | `get_customer_balance`, `register_payment` |
| 4 | Proveedores y órdenes de compra | Catálogo de proveedores, OC que suma inventario | Schema proveedores · schema OC · recepción → inventario · UI | `list_suppliers`, `create_purchase_order` |
| 5 | Facturación mock (CFDI) | Generar XML tipo CFDI de una venta | Mapeo venta → CFDI · generador XML · validación · descarga | `generate_invoice_xml`, `get_invoice` |
| 6 | Dashboard de ventas | Ventas por periodo, top productos | Queries de agregación · API · gráficas · filtros | `get_sales_summary`, `get_top_products` |
| 7 | Roles y permisos | Admin / vendedor / almacén | Schema roles · middleware · guardas en UI · seed | `get_user_permissions`, `assign_role` |
| 8 | Importación CSV | Carga masiva de productos con validación | Parser · validación · upsert · reporte de errores | `validate_csv`, `import_products` |

## Requisitos si eliges otro proyecto

Cualquier proyecto sirve si cumple esto antes de la clase 1:

- [ ] Repo git propio que corre localmente con un comando documentado
- [ ] Una feature acotada que se divida en 3–5 tareas independientes (backend, datos, UI, pruebas)
- [ ] Sin código ni datos confidenciales que no puedan mostrarse en la demo o enviarse a Claude
- [ ] Un dominio con 2–3 operaciones que tenga sentido exponer como MCP tools
- [ ] Stack que ya domines: el workshop enseña Claude Code, no el framework

## Checklist de terminado

El capstone está terminado cuando puedes marcar los 6 puntos antes de la demo:

- [ ] `CLAUDE.md` y `AGENTS.md` con la sección de tu feature
- [ ] 2 o más custom agents en `.claude/agents/` con tools mínimas
- [ ] Change de OpenSpec con `tasks.md` actualizado tarea por tarea
- [ ] Al menos 1 merge desde un worktree a la rama de feature
- [ ] MCP server con 2 o más tools, conectado y probado desde Claude Code
- [ ] Script headless de code review que corre sin errores

## Formato de la demo

La demo dura 30 min por grupo: 8 presentaciones de 3 min (24 min) y 6 min de retrospectiva. Es al cierre de la clase 3 (2:00–2:30 PM Grupo A, 5:00–5:30 PM Grupo B).

1. **30 s — La spec:** qué feature elegiste y qué tareas marcaste como `[P]`.
2. **60 s — El Agent Team:** el team corriendo, o el resultado del merge desde los worktrees.
3. **60 s — MCP o headless:** una MCP tool de tu dominio o el review headless, en vivo.
4. **30 s — Lección aprendida:** un punto donde el agente falló y cómo lo corregiste.

Reglas:

- El orden de presentación se define al inicio de la clase 3.
- Se cronometra con alarma a los 3 min.
- Si algo falla en vivo, se muestra la rama de checkpoint (o tu tag de respaldo si usas otro proyecto).

La retrospectiva cierra con una pregunta: ¿cuándo vale la pena el costo de tokens de un Agent Team?
