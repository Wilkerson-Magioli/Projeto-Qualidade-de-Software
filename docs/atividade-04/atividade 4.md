
# Atividade 4 — Testes Funcionais vs Estruturais – LocalEats

## 1. Funcionalidade escolhida

Funcionalidade: Busca de restaurantes

O sistema permite buscar restaurantes por:
- culinária
- localização
- preço

Usuário espera:
- resultados corretos
- filtros funcionando
- rapidez

---

## 2. Testes Caixa-Preta

Entradas possíveis:
- busca por culinária
- busca por preço
- múltiplos filtros
- busca vazia

Comportamentos esperados:
- resultados corretos
- mensagem quando não houver resultados
- tempo de resposta adequado

Situações de erro:
- restaurantes incorretos
- resultados vazios indevidos
- lentidão
- filtros ignorados

---

## 3. Testes Caixa-Branca

Possível implementação:
- if filtro culinária
- if filtro localização
- if preço
- validação parâmetros
- consulta banco dados

Situações para testar:
- cada condição isolada
- múltiplos filtros
- parâmetros vazios
- erros de lógica
- tratamento exceções

---

## 4. Comparação

Caixa-preta:
- visão usuário
- valida funcionalidade
- encontra erros visíveis

Caixa-branca:
- visão código
- valida lógica interna
- encontra erros estruturais

---

## 5. Reflexão

Ambas abordagens são necessárias.

Caixa-preta:
- valida experiência usuário

Caixa-branca:
- encontra erros internos

Somente uma abordagem não é suficiente.
