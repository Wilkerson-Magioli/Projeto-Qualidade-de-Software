# Aula 09 — Testes Unitários Automatizados e TDD – LocalEats

## 1. Funcionalidade escolhida

### Funcionalidade
Cálculo de taxa de entrega

### O que faz
Calcula o valor da entrega com base na distância entre o restaurante e o cliente.

### Problema que resolve
Padroniza a cobrança da entrega e evita cálculos incorretos.

### Importância
Impacta diretamente o valor final do pedido e a experiência do usuário.

### Regras de negócio
- Até 3 km → taxa fixa de R$ 5,00
- Acima de 3 km → R$ 5,00 + R$ 2,00 por km excedente
- Distância negativa → erro

---

## 2. Implementação da Função

```python
def calcular_taxa_entrega(distancia):
    if distancia < 0:
        raise ValueError("Distância inválida")

    if distancia <= 3:
        return 5

    return 5 + ((distancia - 3) * 2)
```

---

## 3. Testes Unitários

### Teste 1 — Deve calcular taxa fixa até 3 km

```python
def test_deve_calcular_taxa_fixa():
    resultado = calcular_taxa_entrega(2)
    assert resultado == 5
```

### Teste 2 — Deve calcular taxa proporcional acima de 3 km

```python
def test_deve_calcular_taxa_proporcional():
    resultado = calcular_taxa_entrega(5)
    assert resultado == 9
```

### Teste 3 — Deve gerar erro para distância negativa

```python
import pytest

def test_deve_gerar_erro_distancia_negativa():
    with pytest.raises(ValueError):
        calcular_taxa_entrega(-1)
```

---

## 4. Aplicação do TDD

### Red
O teste foi escrito antes da implementação e inicialmente falhou.

### Green
Foi implementada a lógica mínima necessária para fazer o teste passar.

### Refactor
O código foi reorganizado para melhorar legibilidade e manutenção.

---

## 5. Refatoração

Melhorias realizadas:
- nomes mais claros
- simplificação das condições
- melhor organização da lógica

---

## 6. Execução dos Testes

- Total de testes: 3
- Passaram: 3
- Falharam: 0

Evidência:

```bash
3 passed in 0.01s
```

---

## 7. Reflexão no contexto do LocalEats

O TDD ajudou a organizar o desenvolvimento e aumentou a confiança no código.

Os testes automatizados ajudam a evitar regressões e facilitam manutenção futura.
