```mermaid
graph TD
    User((Usuario/Gamer)) -->|Interactúa| FE[Frontend - React.js]
    
    subgraph "Plataforma LevelUpGamer"
        FE -->|API Calls| AGW[API Gateway / Punto de Entrada]
        
        subgraph "Capa de Microservicios"
            AGW --> MS1[Microservicio: Usuarios/Auth]
            AGW --> MS2[Microservicio: Catálogo de Juegos]
            AGW --> MS3[Microservicio: Torneos/Ranking]
            AGW --> MS4[Microservicio: Notificaciones]
        end
        
        subgraph "Capa de Datos"
            MS1 --- DB1[(DB Usuarios)]
            MS2 --- DB2[(DB Catálogo)]
            MS3 --- DB3[(DB Torneos)]
            MS4 --- DB4[(DB Logs)]
        end
    end

    style FE fill:#61dafb,stroke:#333,stroke-width:2px,color:#000
    style AGW fill:#f9f,stroke:#333,stroke-width:2px
    style MS1 fill:#6db33f,stroke:#fff,color:#fff
    style MS2 fill:#6db33f,stroke:#fff,color:#fff
    style MS3 fill:#6db33f,stroke:#fff,color:#fff
    style MS4 fill:#6db33f,stroke:#fff,color:#fff
