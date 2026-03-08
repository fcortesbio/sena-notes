# Gráfica de Relaciones Externas (Ecosistema de Negocio)

Este diagrama posiciona a la constructora en el centro (sistema abierto) y muestra cómo interactúa con el entorno para captar entradas y entregar salidas.

```mermaid
graph LR
    %% Actores Externos (Entradas)
    PV[Proveedores de Materiales]
    AQ[Aliados: Arquitectos/Inmobiliarias]
    
    %% Centro del Sistema
    subgraph AME_GROUP_SPA [AME Group SpA]
        direction TB
        Ventas[Software de Ventas/CRM]
        Construccion[Procesos de Construcción]
    end
    
    %% Salidas y Entorno
    CL[Cliente Final]
    ENT[Entorno Social y Económico]

    %% Flujos de Relación
    PV --> |Insumos y Materias Primas| Construccion
    AQ <--> |Referidos y Diseño Conjunto| Ventas
    Ventas --> |Propuesta Comercial y 3D| CL
    CL --> |Requisitos y Feedback| Ventas
    Construccion --> |Vivienda Finalizada| CL
    AME_GROUP_SPA --- ENT

    %% Estética
    style AME_GROUP_SPA fill:#fff4dd,stroke:#d4a017,stroke-width:2px
    style CL fill:#f96,stroke:#333,stroke-width:2px
    style AQ fill:#9cf,stroke:#333
```


```mermaid
graph LR

subgraph Entorno_Entrada [REQUERIMIENTOS / NECESIDADES]

direction TB

E1[Necesidad Habitacional]

E2[Requisitos del Cliente]

end

  

subgraph Mapa_de_Procesos [MAPA DE PROCESOS: AME GROUP SpA]

direction LR

subgraph Estrategicos [PROCESOS ESTRATÉGICOS]

direction TB

S1[Dirección General / Liderazgo]

S2[Planeación y Marketing]

S3[Gestión de Calidad]

end

  

subgraph Clave [PROCESOS MISIONALES / CLAVE]

direction TB

C1[Ventas y Cotización] --> C2[Planificación y Diseño]

C2 --> C3[Producción y Construcción]

C3 --> C4[Entrega de Vivienda]

end

  

subgraph Apoyo [PROCESOS DE APOYO]

direction LR

A1[Administración y Finanzas]

A2[Compras / Contabilidad]

A3[Gestión Humana / Legal]

end

end

  

subgraph Entorno_Salida [SATISFACCIÓN DEL CLIENTE]

S_Out[Vivienda Finalizada]

F_Back[Fidelización / Feedback]

end

  

%% Relaciones de flujo principal

Entorno_Entrada --> C1

C4 --> Entorno_Salida

  

%% Relaciones de control y soporte

Estrategicos --> Clave

Clave --> Estrategicos

Apoyo <--> Clave

Apoyo <--> Estrategicos

  

%% Estilos

style Estrategicos fill:#ADD8E6,stroke:#005f73,stroke-width:2px

style Clave fill:#FFD700,stroke:#9b2226,stroke-width:2px

style Apoyo fill:#E6E6FA,stroke:#5c4d7d,stroke-width:2px

style Entorno_Entrada fill:#2ecc71,color:#fff

style Entorno_Salida fill:#2ecc71,color:#fff
```
