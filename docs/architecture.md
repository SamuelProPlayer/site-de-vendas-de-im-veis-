# Especificação Técnica e Arquitetura

## 1. Visão Geral da Arquitetura
A aplicação será desenvolvida utilizando HTML5, CSS3 e JavaScript (ES6+) no Front-end. Os dados serão manipulados no cliente e persistidos através do `localStorage` (ou API simulada via JSON-Server/Fetch API) para garantir a funcionalidade dinâmica.

## 2. Modelo de Dados (Diagrama Entidade-Relacionamento)

O diagrama abaixo representa as entidades principais do sistema e como elas se relacionam entre si.

```mermaid
erDiagram
    USUARIO ||--o{ DISCIPLINA : possui
    DISCIPLINA ||--o{ TAREFA : contem

    USUARIO {
        string id PK
        string nome
        string email
        string senha
    }

    DISCIPLINA {
        string id PK
        string usuario_id FK
        string nome
        string professor
    }

    TAREFA {
        string id PK
        string disciplina_id FK
        string titulo
        string descricao
        date data_entrega
        string prioridade
        boolean concluida
    }
