# Nome: Henrique Yuji Isogai Yoneoka
# RA: 10418153

# Diagrama 
``` mermaid
classDiagram
    class MEC {
        +string nome
        +regulamentar()
    }

    class InstituicaoDeEnsinoSuperior {
        +string nome
        +string cnpj
        +credenciarCurso()
    }

    class UnidadeAcademica {
        +string nome
        +int id
        +gerenciarCursos()
    }

    class Professor {
        +string nome
        +string matricula
        +ensinar()
        +avaliarAluno()
    }

    class Aluno {
        +string nome
        +string matricula
        +estudar()
        +serAvaliado()
    }

    class Avaliacao {
        +int id
        +string tipo
        +date data
        +double nota
        +registrar()
    }

    class Curso {
        +string nome
        +string codigo
        +string modalidade
        +adicionarComponente()
        +definirPPC()
    }

    class ProjetoPedagogicoDeCurso {
        +int id
        +date dataAprovacao
        +string objetivos
        +validar()
    }

    class DiretrizCurricularNacional {
        +int id
        +string descricao
        +estabelecerPadroes()
    }

    class PerfilDeIngressante {
        +int id
        +string descricao
    }

    class PerfilDeEgresso {
        +int id
        +string descricao
    }

    class ComponenteCurricular {
        +string nome
        +string codigo
        +int cargaHoraria
        +verificarPreRequisitos()
    }

    class Ementa {
        +int id
        +string conteudoProgramatico
        +string bibliografiaBasica
        +definirConteudo()
    }

    class Competencia {
        +int id
        +string descricao
        +string tipo
    }
    
    class Turma {
        +string codigo
        +int numeroVagas
        +string status
        +matricularAluno()
        +alocarProfessor()
    }

    class Aula {
        +date data
        +string assunto
        +string local
        +registrarFrequencia()
    }

    class Calendario {
        +int ano
        +string periodoLetivo
        +estabelecerDatas()
    }

    %% Relacionamentos

    MEC "1" -- "0..*" InstituicaoDeEnsinoSuperior : regula
    InstituicaoDeEnsinoSuperior "1" -- "1..*" UnidadeAcademica : possui
    UnidadeAcademica "1" -- "1..*" Curso : oferece
    UnidadeAcademica "1" -- "0..*" ComponenteCurricular : oferece
    
    Curso "1" o-- "1" ProjetoPedagogicoDeCurso : possui
    ProjetoPedagogicoDeCurso "1" -- "1" DiretrizCurricularNacional : segue
    ProjetoPedagogicoDeCurso "1" o-- "1" PerfilDeIngressante : define
    ProjetoPedagogicoDeCurso "1" o-- "1" PerfilDeEgresso : define
    ProjetoPedagogicoDeCurso "1" o-- "0..*" Competencia : define

    Curso "1" o-- "1..*" ComponenteCurricular : compoe
    ComponenteCurricular "1" -- "1" Ementa : tem
    ComponenteCurricular "1" -- "0..*" Competencia : desenvolve

    Curso "1" o-- "1..*" Turma : oferece
    Turma "1" -- "1..*" Aluno : matricula
    Turma "1" -- "1" Professor : aloca
    Turma "1" o-- "1..*" Aula : tem
    
    Aluno "1" -- "0..*" Avaliacao : éAvaliadoEm
    Professor "1" -- "0..*" Avaliacao : realiza
    
    Calendario "1" -- "0..*" Turma : organiza
    Calendario "1" -- "0..*" Aula : organiza
