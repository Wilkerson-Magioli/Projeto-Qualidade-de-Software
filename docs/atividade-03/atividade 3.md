
# Atividade 3 — Estratégia Inicial de Testes – LocalEats

## 1. Funcionalidades principais

- Busca de restaurantes por culinária, localização e preço  
- Visualização de cardápios, fotos e avaliações  
- Salvar restaurantes favoritos  
- Recomendações personalizadas  
- Compartilhar avaliações  
- Consistência entre web e mobile  

---

## 2. Níveis de teste

### Busca de restaurantes
- Unitário: lógica de filtros e validação de parâmetros  
- Integração: frontend + API + banco de dados  
- Sistema: fluxo completo de busca com filtros  
- Aceitação: usuário encontra restaurantes corretamente  

### Visualização de restaurante
- Unitário: renderização e formatação de dados  
- Integração: API + imagens + avaliações  
- Sistema: abrir página do restaurante  
- Aceitação: usuário visualiza informações corretamente  

### Favoritos
- Unitário: adicionar/remover favoritos  
- Integração: autenticação + banco  
- Sistema: salvar e listar favoritos  
- Aceitação: usuário salva favoritos  

### Recomendações
- Unitário: regras de recomendação  
- Integração: histórico + API  
- Sistema: recomendações exibidas  
- Aceitação: sugestões relevantes  

---

## 3. Prioridades e riscos

Funcionalidades críticas:

- Busca de restaurantes → impacto direto no uso do sistema  
- Avaliações → perda de dados afeta confiança  
- Consistência web/mobile → comportamento diferente gera erro  
- Desempenho → lentidão em horários de pico  

---

## 4. Pirâmide de testes

Maior quantidade:
- Testes unitários

Quantidade média:
- Testes de integração

Menor quantidade:
- Testes de sistema e aceitação

Justificativa:
- menor custo nos testes unitários
- maior cobertura lógica
- testes E2E mais caros e lentos

---

## 5. Testes em produção

Utilização:
- monitoramento de performance
- feature flags
- canary release
- validação em dispositivos reais

Justificativa:
Permite identificar problemas reais sem impactar todos usuários.
