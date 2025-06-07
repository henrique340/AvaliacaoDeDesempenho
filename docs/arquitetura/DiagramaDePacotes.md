```mermaid
  
 classDiagram
    class Autenticacao {
        +Login/Logout
        +OAuth
        +JWT
    }
    class Usuarios {
        +Cadastro
        +Edição
        +Exclusão
        +Perfis
    }
    class Avaliacoes {
        +Criação
        +Envio
        +Preenchimento
        +Autoavaliação
        +Armazenamento
    }
    class Criterios {
        +Definição
        +Edição
        +Exclusão
    }
    class RelatoriosBI {
        +Relatórios Individuais
        +Relatórios por Setor
        +Matriz 9-box
        +Exportação PDF/CSV
        +Dashboard
    }
    class Notificacoes {
        +E-mail
        +Painel
    }
    class SegurancaLogs {
        +Criptografia
        +HTTPS
        +Logs de Ações
    }
    class Integracoes {
        +ERPs
        +Plataformas RH
    }
    class Documentacao {
        +Manual de Uso
        +API REST
    }

    Autenticacao --> Usuarios : autentica
    Usuarios --> Avaliacoes : realiza
    Avaliacoes --> Criterios : utiliza
    Avaliacoes --> RelatoriosBI : gera dados
    Avaliacoes --> Notificacoes : dispara
    Avaliacoes --> SegurancaLogs : registra
    Usuarios --> SegurancaLogs : registra
    RelatoriosBI --> Avaliacoes : consulta dados
    SegurancaLogs --> Integracoes : monitora
    Avaliacoes --> Integracoes : integra
    Documentacao --> Usuarios : orienta
    Documentacao --> Avaliacoes : orienta
