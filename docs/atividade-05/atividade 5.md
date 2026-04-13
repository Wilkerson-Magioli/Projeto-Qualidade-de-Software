
# Atividade 5 — Planejamento e Execução de Testes – LocalEats

## 1. Plano de Testes

### Objetivo
Validar funcionalidades principais do LocalEats.

### Escopo
Testar:
- busca
- visualização
- favoritos
- avaliações

Não testar:
- desempenho avançado
- integrações externas

### Estratégia
Testes funcionais manuais caixa-preta.

### Responsáveis
QA → execução  
Dev → correção  
PO → validação  

---

## 2. Casos de Teste

### CT01 — Busca com sucesso
Pré-condição: sistema aberto  
Passos: buscar culinária  
Resultado esperado: lista correta  

### CT02 — Visualizar restaurante
Pré-condição: lista exibida  
Passos: abrir restaurante  
Resultado esperado: detalhes exibidos  

### CT03 — Favorito sucesso
Pré-condição: usuário logado  
Passos: adicionar favorito  
Resultado esperado: salvo  

### CT04 — Busca sem resultado
Pré-condição: busca inválida  
Resultado esperado: mensagem  

### CT05 — Avaliação inválida
Pré-condição: avaliação vazia  
Resultado esperado: bloqueio  

---

## 3. Execução

CT01 — Passou  
CT02 — Passou  
CT03 — Falhou  
CT04 — Passou  
CT05 — Falhou  

---

## 4. Análise

Executados: 5  
Passaram: 3  
Falharam: 2  

Problemas:
- favorito não salva
- avaliação inválida aceita

---

## 5. Reflexão

Plano ajudou organizar testes.
Execução revelou problemas.
Melhoria:
- mais cenários negativos
- automação futura
