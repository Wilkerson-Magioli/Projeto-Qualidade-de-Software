# Aula 14 — Qualidade de Processo – LocalEats

## 1. Mapeamento do Processo Atual

### Fluxo do Processo

A equipe segue um fluxo contínuo de desenvolvimento e validação das funcionalidades do LocalEats. O processo inicia com o recebimento da demanda, passa pela análise dos requisitos, implementação da solução, execução dos testes e, caso sejam encontrados defeitos, retorna para a etapa de correção. Após a validação final, a funcionalidade é disponibilizada em produção.

#### Diagrama (Mermaid)

```mermaid
flowchart LR
    A([Recebimento da Demanda])
    B([Análise dos Requisitos])
    C([Desenvolvimento])
    D([Testes])
    E{Defeitos encontrados?}
    F([Correções])
    G([Validação Final])
    H([Entrega / Deploy])

    A --> B
    B --> C
    C --> D
    D --> E
    E -- Sim --> F
    F --> D
    E -- Não --> G
    G --> H

    style A fill:#E3F2FD,stroke:#1565C0
    style B fill:#E8F5E9,stroke:#2E7D32
    style C fill:#FFF8E1,stroke:#F9A825
    style D fill:#F3E5F5,stroke:#6A1B9A
    style E fill:#FFEBEE,stroke:#C62828
    style F fill:#FBE9E7,stroke:#D84315
    style G fill:#E8F5E9,stroke:#2E7D32
    style H fill:#E3F2FD,stroke:#1565C0
```

O diagrama evidencia que a qualidade é verificada continuamente durante o processo. Sempre que um defeito é identificado nos testes, o fluxo retorna para a etapa de correções, garantindo que apenas funcionalidades validadas sejam entregues aos usuários.

---

## 2. Tabela de Entradas, Atividades e Saídas

| Etapa                 | Entrada                  | Atividade                         | Saída                   |
|:----------------------|:-------------------------|:----------------------------------|:------------------------|
| Recebimento da demanda | Solicitação do cliente   | Levantar e registrar a necessidade | Requisito documentado   |
| Análise dos requisitos | Requisito documentado    | Refinar regras de negócio         | Especificação funcional |
| Desenvolvimento        | Especificação funcional  | Implementar a funcionalidade      | Código desenvolvido     |
| Testes                 | Código desenvolvido      | Executar testes                   | Relatório de testes     |
| Correções              | Defeitos identificados   | Corrigir os problemas encontrados | Código corrigido        |
| Validação final        | Código corrigido         | Confirmar os requisitos           | Funcionalidade aprovada |
| Entrega                | Funcionalidade aprovada  | Publicar em produção              | Sistema atualizado      |

---

## 3. Reflexão sobre o Processo

### O processo utilizado pela equipe está claramente definido?

De forma geral sim, porém a documentação pode ser aprimorada para padronizar as atividades.

### Todos os integrantes seguem o mesmo fluxo de trabalho?

Esse deve ser o objetivo da equipe. A padronização reduz retrabalho e melhora a comunicação.

### Em quais etapas a qualidade é verificada?

- Análise dos requisitos
- Desenvolvimento
- Testes
- Validação final

### Quais melhorias poderiam tornar o processo mais eficiente?

- Code Review
- Integração Contínua (CI)
- Testes automatizados
- Critérios de aceitação bem definidos
- Checklists antes do deploy

### Como a qualidade do processo impacta a qualidade do produto final?

Um processo organizado reduz defeitos, melhora a comunicação entre os integrantes, aumenta a produtividade e gera um software mais confiável e de melhor qualidade.

---

## Conclusão

A qualidade do processo influencia diretamente a qualidade do software. A adoção de boas práticas, revisão contínua e testes em todas as etapas contribui para entregas mais seguras e maior satisfação dos usuários do LocalEats.
