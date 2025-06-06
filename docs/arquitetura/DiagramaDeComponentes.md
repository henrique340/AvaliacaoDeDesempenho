```mermaid
classDiagram
    class Frontend {
      <<component>>
      React.js
    }
    class Backend {
      <<component>>
      FastAPI
    }
    class Auth {
      <<component>>
      OAuth
    }
    class Notificacoes {
      <<component>>
      Email/Push
    }
    class Exportacao {
      <<component>>
      PDF/CSV
    }
    class BI {
      <<component>>
      Chart.js
    }
    class Logs {
      <<component>>
      Auditoria
    }
    class Integracao {
      <<component>>
      ERP/RH
    }
    class DB {
      <<database>>
      PostgreSQL
    }
    class AWS {
      <<cloud>>
      AWS Cloud
    }

    Frontend --|> Backend : REST API
    Backend -- Auth : OAuth
    Backend -- Notificacoes
    Backend -- Exportacao
    Backend -- BI
    Backend -- Logs
    Backend -- Integracao
    Backend -- DB
    Frontend -- BI
    Backend -- AWS
    DB -- AWS
    Auth -- AWS
    Notificacoes -- AWS
    Exportacao -- AWS
    BI -- AWS
    Logs -- AWS
    Integracao -- AWS
