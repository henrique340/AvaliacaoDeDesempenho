```mermaid
flowchart TD
    %% Usuário acessa via navegador
    User["Usuário (Navegador Web)"]

    %% AWS Cloud (nó principal de implantação)
    subgraph AWS_Cloud["AWS Cloud"]
        FE["Frontend (React.js)"]
        BE["Backend API (FastAPI)"]
        AUTH["Serviço de Autenticação (OAuth)"]
        NOTIF["Serviço de Notificações (Email/Push)"]
        EXPORT["Serviço de Exportação (PDF/CSV)"]
        BI["Dashboard/BI (Chart.js)"]
        LOGS["Serviço de Logs (Auditoria)"]
        INTEG["Integração ERP/RH"]
        DB["Banco de Dados (PostgreSQL)"]
    end

    %% Fluxo de comunicação
    User -- "HTTPS" --> FE
    FE -- "REST API" --> BE
    BE -- "OAuth" --> AUTH
    BE -- "Notificações" --> NOTIF
    BE -- "Exportação" --> EXPORT
    BE -- "BI" --> BI
    BE -- "Logs" --> LOGS
    BE -- "Integração" --> INTEG
    BE -- "CRUD" --> DB
    FE -- "Gráficos" --> BI

    %% Todos os componentes estão hospedados na AWS Cloud
