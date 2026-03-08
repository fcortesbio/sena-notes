
# Gráfica de Relaciones Internas (Diagrama de Red)
Este gráfico muestra la interconexión entre la Dirección General y los subsistemas operativos, destacando la fluidez de la información técnica y financiera.


```mermaid
graph TD
    %% Definición de Nodos
    DG[Dirección General]
    AD[Admin. y Finanzas]
    PL[Planificación y Diseño]
    PR[Área de Producción]
    GE[Gestión Fiscal y Legal]

    %% Relaciones de Información Financiera
    DG <--> |Presupuestos y Metas| AD
    AD -.-> |Reportes de Costos| DG
    AD <--> |Flujo de Caja y Contratos| GE
    
    %% Relaciones de Información Técnica
    DG <--> |Directrices de Proyecto| PL
    PL <--> |Planos y Especificaciones| PR
    PR -.-> |Estado de Obra e Insumos| DG
    
    %% Relaciones Transversales
    AD -.-> |Recursos para Insumos| PR
    GE -.-> |Validación de Normativa| PL

    %% Estética
    style DG fill:#f9f,stroke:#333,stroke-width:2px
    style PR fill:#bbf,stroke:#333
    style AD fill:#dfd,stroke:#333
```

