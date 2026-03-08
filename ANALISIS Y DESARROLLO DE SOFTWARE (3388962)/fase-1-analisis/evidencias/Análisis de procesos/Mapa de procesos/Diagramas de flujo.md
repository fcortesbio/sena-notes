
# Mapa de proceso

Aquí almacenamos el codigo fuente de los diagramas de procesos para control de versiones

## MACRO-PROCESO: MISIONAL (CLAVE)

### Gestión Comercial y Ventas

```mermaid
graph TD

   %% Inicio y Entradas

   Inicio([Inicio]) --> IngresoDatos[/Entrada: Datos y encuesta del Cliente/]

   %% Procesos y Decisiones

   IngresoDatos --> ProcAnalitica[Proceso: Ejecutar Motor de Analítica / Lead Scoring]

   ProcAnalitica --> DecCalificacion{¿Puntaje Alto / Cliente Potencial?}

   %% Rama Si (Potencial)

   DecCalificacion -->|Sí| HabilitarAcceso[Proceso: Habilitar acceso a visualización 3D]

   HabilitarAcceso --> GenerarCot[Proceso: Generar cotización automatizada]

   GenerarCot --> SalidaCot[/Salida: Cotización preliminar enviada al cliente/]

   SalidaCot --> DecCompra{¿Cliente acepta propuesta?}

   DecCompra -->|Sí| SalidaVenta[/Salida: Confirmación de cierre de venta/]

   SalidaVenta --> Fin([Fin del Proceso Comercial / Pasa a Producción])

   %% Rama No/Indeciso

   DecCalificacion -->|No| Tracking[Proceso: Activar Tracking de Indecisos]

   DecCompra -->|No| Tracking

   Tracking --> CampanaNutricion[Proceso: Ejecutar campaña de nutrición / Retargeting]

   CampanaNutricion --> SalidaCorreos[/Salida: Correos y pruebas de valor enviadas/]

   SalidaCorreos --> Fin
```


### Planificación y Diseño

```mermaid
---

config:

 layout: dagre

---

flowchart TB

   Inicio(["Inicio"]) --> IngresoReq[/"Entrada: Cotización aprobada y Requisitos Técnicos"/]

   IngresoReq --> Analisis["Proceso: Análisis de viabilidad técnica e ingeniería"]

   Analisis --> DecViable{"¿Diseño Viable y Normativo?"}

   DecViable -- No --> AjusteReq["Proceso: Ajustar alcance con Comercial/Cliente"]

   AjusteReq --> Analisis

   DecViable -- Sí --> Modelado["Proceso: Modelado BIM/CAD y Renders"]

   Modelado --> RevCliente["Proceso: Presentación al Cliente"]

   RevCliente --> DecAprobado{"¿Cliente aprueba?"}

   DecAprobado -- No --> AjusteDiseno["Proceso: Modificaciones según feedback"]

   AjusteDiseno --> RevCliente

   DecAprobado -- Sí --> GenMateriales["Proceso: Generar Planos Definitivos y Lista de Materiales"]

   GenMateriales --> SalidaPlanos[/"Salida: Expediente Técnico a Producción y Compras"/]

   SalidaPlanos --> Fin(["Fin del Proceso de Diseño"])
```
