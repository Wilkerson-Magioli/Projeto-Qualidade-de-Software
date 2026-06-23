# Aula 17 – Integração Contínua, Qualidade Automatizada, Métricas e Gestão de Defeitos

## 1. Repositório da Atividade

| Item                | Descrição                                                     |
| ------------------- | ------------------------------------------------------------- |
| Nome do repositório | localeats-ci-laboratorio                                      |
| Link do repositório | https://github.com/Wilkerson-Magioli/localeats-ci-laboratorio |

### Estrutura de Diretórios

```text
localeats-ci-laboratorio/
├── .github/
│   └── workflows/
│       └── quality.yml
├── tests/
│   ├── features/
│   │   └── order_total.feature
│   ├── test_order.py
│   └── test_order_bdd.py
├── order.py
├── requirements.txt
├── pytest.ini
└── aula-17-integracao-continua-qualidade.md
```

---

## 2. Planejamento da Funcionalidade

| Item                       | Descrição                                                                            |
| -------------------------- | ------------------------------------------------------------------------------------ |
| Título da Issue            | Implementar cálculo do valor total do pedido                                         |
| Objetivo da funcionalidade | Permitir que o sistema calcule automaticamente o valor total dos itens de um pedido. |
| Issue utilizada            | #2                                                                                   |

### História de Usuário

Como cliente do LocalEats, desejo visualizar o valor total do pedido para conhecer o valor final da minha compra.

### Critérios de Aceitação

* Somar todos os valores dos itens do pedido;
* Retornar 0 para lista vazia;
* Possuir testes automatizados;
* Validar a funcionalidade por meio de pipeline de integração contínua.

---

## 3. Testes Automatizados

### Teste Unitário

Objetivo: validar se a função realiza corretamente a soma dos itens do pedido.

Casos de teste implementados:

* Soma de itens [10, 20, 30] retornando 60;
* Lista vazia retornando 0.

### Teste BDD

Cenário implementado:

```gherkin
Scenario: Somar os valores dos itens
  Given que o pedido possui os itens 10, 20 e 30
  When o sistema calcula o valor total
  Then o resultado deve ser 60
```

Resultado:

```text
3 passed
```

---

## 4. Pipeline de Integração Contínua

### Workflow

Arquivo:

```text
.github/workflows/quality.yml
```

Objetivo:

* Instalar dependências;
* Executar os testes automatizados;
* Validar a qualidade da implementação a cada push ou pull request.

Trecho principal:

```yaml
name: Quality Check

on:
  push:
  pull_request:

jobs:
  tests:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - uses: actions/setup-python@v5
        with:
          python-version: "3.13"

      - name: Instalar dependências
        run: |
          pip install -r requirements.txt

      - name: Executar testes
        run: pytest
```

Resultado da execução:

Pipeline executado com sucesso no GitHub Actions.

---

## 5. Indicadores de Qualidade

| Indicador          | Resultado |
| ------------------ | --------- |
| Testes executados  | 3         |
| Testes aprovados   | 3         |
| Testes com falha   | 0         |
| Taxa de sucesso    | 100%      |
| Status do Pipeline | Sucesso   |

---

## 6. Registro de Defeito

| Item            | Descrição                                     |
| --------------- | --------------------------------------------- |
| Título          | Bug: cálculo do total não tratava lista vazia |
| Tipo            | Defeito funcional                             |
| Severidade      | Baixa                                         |
| Issue utilizada | #3                                            |

### Descrição

Durante a elaboração dos testes automatizados foi identificado o risco de a funcionalidade não tratar corretamente pedidos sem itens.

Foi criado um teste específico para lista vazia:

```python
assert calculate_total([]) == 0
```

Após a validação, a implementação foi confirmada como correta e o pipeline executou com sucesso.

---

## Conclusão

A atividade permitiu aplicar conceitos de Integração Contínua, Qualidade Automatizada, Testes Unitários, BDD, GitHub Actions, Métricas de Qualidade e Gestão de Defeitos. Todos os testes foram executados com sucesso e o pipeline validou automaticamente a implementação.
