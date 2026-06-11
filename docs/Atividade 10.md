# Aula 15 — Modelos de Maturidade – LocalEats

## 1. Diagnóstico de Maturidade

### Avaliação do Processo

| Critério                                                                                   | Sim |  Parcial | Não |
| :----------------------------------------------------------------------------------------- | :-: | :------: | :-: |
| Os requisitos são documentados?                                                            | ✅  |          |     |
| Existe controle de mudanças?                                                               |     |    ✅    |     |
| Há atividades de teste definidas?                                                          | ✅  |          |     |
| Os defeitos são registrados?                                                               |     |    ✅    |     |
| O processo de desenvolvimento é conhecido por toda a equipe?                               |     |    ✅    |     |
| As tarefas são planejadas e acompanhadas regularmente?                                     | ✅  |          |     |
| Existe padronização para implementação de funcionalidades?                                 |     |    ✅    |     |
| Os testes são executados antes da entrega das funcionalidades?                             | ✅  |          |     |
| Há revisão de código ou validação por outro integrante da equipe?                          |     |    ✅    |     |
| A equipe utiliza ferramentas para gerenciamento das atividades?                            | ✅  |          |     |
| Os artefatos do projeto (requisitos, testes e código) são organizados e versionados?       | ✅  |          |     |
| Existe rastreabilidade entre requisitos e funcionalidades implementadas?                   |     |    ✅    |     |
| A equipe realiza reuniões ou retrospectivas para identificar melhorias?                    |     |          | ✅  |
| Existem indicadores ou métricas para acompanhar a qualidade do projeto?                    |     |          | ✅  |

### Classificação do Processo

**Nível identificado:** **Gerenciado**

**Justificativa**

O processo apresenta planejamento das atividades, documentação básica dos requisitos, utilização de controle de versão, execução de testes e organização dos artefatos. Entretanto, ainda existem lacunas relacionadas ao uso de métricas, retrospectivas, rastreabilidade completa e padronização de algumas práticas. Assim, o processo já é gerenciado, porém ainda não possui o nível de formalização necessário para ser considerado um processo totalmente definido segundo os conceitos de maturidade apresentados por modelos como CMMI e MPS.BR.

---

## 2. Lacunas Identificadas

| Lacuna                                                     | Impacto                                                         |
|:---------------------------------------------------------- |:--------------------------------------------------------------- |
| Ausência de indicadores de qualidade                       | Dificulta acompanhar a evolução do projeto e medir resultados.  |
| Falta de retrospectivas periódicas                         | Reduz a identificação de melhorias contínuas no processo.       |
| Rastreabilidade parcial entre requisitos e funcionalidades | Dificulta identificar impactos das mudanças e validar entregas. |
| Revisão de código não padronizada                          | Aumenta o risco de defeitos chegarem à produção.                |

---

## 3. Propostas de Melhoria

| Melhoria                                                           | Benefício                                                         |
|:-------------------------------------------------------------------|:------------------------------------------------------------------|
| Implantar métricas de qualidade (defeitos, cobertura e retrabalho) | Permite monitorar a evolução do processo com dados objetivos.     |
| Realizar retrospectivas ao final de cada entrega                   | Promove melhoria contínua e compartilhamento de conhecimento.     |
| Padronizar revisões de código (Code Review)                        | Reduz defeitos e melhora a qualidade do código.                   |
| Implementar rastreabilidade entre requisitos, tarefas e testes     | Facilita manutenção, auditoria e validação das funcionalidades.   |

---

## Conclusão

A análise demonstra que a equipe do LocalEats possui um processo organizado e já adota diversas boas práticas de qualidade, como versionamento, planejamento e execução de testes. Contudo, para evoluir em direção aos níveis superiores de maturidade, é necessário fortalecer práticas de melhoria contínua, medição do processo, rastreabilidade e padronização. Essas ações tornam o desenvolvimento mais previsível, reduzem riscos e contribuem diretamente para a entrega de um software com maior qualidade.
