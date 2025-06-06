``` mermaid
classDiagram
    %% Herança
    class Usuario {
        +int id
        +string nome
        +string email
        +string senha
        +Perfil perfil
    }
    class Colaborador {
        +string setor
        +autoAvaliar()
        +verHistorico()
    }
    class Gestor {
        +criarAvaliacao()
        +enviarAvaliacao()
        +verHistorico()
    }
    class RH {
        +criarAvaliacao()
        +gerar9Box()
        +verHistorico()
        +gerarRelatorio()
    }
    class Admin {
      +int id
      +criar_avaliação()
      +ver_desempenho()
      +gerar_relatório()
}

    Usuario <|-- Colaborador
    Usuario <|-- Gestor
    Usuario <|-- RH
    Usuario <|-- Admin

    %% Associações e agregações
    Gestor "0..*" o-- "0..*" Colaborador : subordinados
    Gestor "0..*" -- "0..*" Avaliacao : cria
    RH "0..*" -- "0..*" Avaliacao : cria
    Colaborador "1" -- "0..*" Avaliacao : avaliado

    %% Avaliação e seus relacionamentos
    class Avaliacao {
        +int id
        +date data
        +string status
        +preencher()
        +enviar()
        +visualizar()
    }
    class Criterio {
        +int id
        +string nome
        +string descricao
        +float peso
        +editar()
        +excluir()
    }
    class Resposta {
        +string valor
    }
    class RelatorioDesempenho {
        +int id
        +string periodo
        +gerarPDF()
        +gerarCSV()
        +visualizar()
    }

    Avaliacao "1" o-- "1..*" Criterio : criterios
    Avaliacao "1" *-- "1..*" Resposta : respostas
    Avaliacao "1" -- "1" Gestor : gestor
    Avaliacao "1" -- "1" RH : rh
    Avaliacao "1" -- "1" Colaborador : avaliado

    RelatorioDesempenho "1" -- "1" Colaborador : colaborador
    RelatorioDesempenho "1" o-- "0..*" Avaliacao : avaliacoes
