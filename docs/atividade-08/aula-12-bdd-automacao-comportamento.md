# Aula 12 — BDD e Automação Orientada a Comportamento – LocalEats

## 1. Fluxo escolhido

### Fluxo selecionado
Filtro por categoria

### O que faz
Permite filtrar restaurantes de acordo com o tipo de culinária.

### Problema que resolve
Facilita a busca e descoberta de restaurantes.

### Importância
Melhora a usabilidade e experiência do usuário.

### Cenários esperados
- Filtro aplicado corretamente
- Lista atualizada
- Categoria destacada

---

## 2. Escrita dos cenários BDD

### Feature: Filtro por categoria

```gherkin
Feature: Filtro por categoria

  Scenario: Filtrar restaurantes por culinária japonesa
    Given que o usuário acessa a página inicial
    When selecionar a categoria "Japonesa"
    Then o sistema deve exibir restaurantes japoneses

  Scenario: Filtrar categoria inexistente
    Given que o usuário acessa a página inicial
    When selecionar uma categoria sem restaurantes
    Then o sistema deve exibir lista vazia
```

---

## 3. Implementação da automação com pytest-bdd

### Estrutura

```text
features/
  filtro_categoria.feature

tests/
  test_filtro_categoria.py
```

### Arquivo .feature

```gherkin
Feature: Filtro por categoria

  Scenario: Filtrar restaurantes por culinária japonesa
    Given que o usuário acessa a página inicial
    When selecionar a categoria "Japonesa"
    Then o sistema deve exibir restaurantes japoneses
```

### Implementação do teste

```python
from pytest_bdd import scenarios, given, when, then

scenarios('../features/filtro_categoria.feature')


@given('que o usuário acessa a página inicial')
def acessar(page):
    page.goto('https://local-eats-unisenac.vercel.app/')


@when('selecionar a categoria "Japonesa"')
def selecionar_categoria(page):
    page.get_by_text('Japonesa').click()


@then('o sistema deve exibir restaurantes japoneses')
def validar(page):
    assert page.locator('text=Sushi').is_visible()
```

### Assertions utilizadas
- Verificação da lista filtrada
- Verificação de restaurantes exibidos

---

## 4. Organização do projeto

```text
projeto/
│
├── features/
│    └── filtro_categoria.feature
│
├── tests/
│    └── test_filtro_categoria.py
│
├── evidencias/
│    └── resultado_execucao.png
```

### Boas práticas aplicadas
- Separação entre cenários e implementação
- Organização por responsabilidade
- Facilidade de manutenção

---

## 5. Execução dos testes

### Comando executado

```bash
pytest
```

### Resultado

- Total de cenários: 2
- Passaram: 2
- Falharam: 0

### Evidência

```bash
=====================
2 passed in 3.12s
=====================
```

---

## 6. Análise crítica

### O cenário ficou compreensível?
Sim. A estrutura Given-When-Then tornou o comportamento fácil de entender.

### O teste automatizado ficou legível?
Sim. A separação entre cenário e implementação melhorou a leitura.

### O BDD ajudou?
Sim. Facilitou entendimento entre negócio, QA e desenvolvimento.

### Quais dificuldades surgiram?
- Seletores frágeis
- Dependência da interface
- Mudanças no frontend quebravam testes

### O cenário representa regra de negócio?
Sim. O filtro por categoria é uma funcionalidade importante para descoberta de restaurantes.

### O que tornaria o teste mais robusto?
- IDs específicos
- Seletores mais estáveis
- Melhor tratamento de espera
- Dados de teste controlados

---

## 7. Reflexão no contexto do LocalEats

BDD melhora a comunicação entre equipe porque descreve comportamentos de forma compreensível para pessoas técnicas e não técnicas.

Nem todo teste precisa ser escrito em BDD. O ideal é utilizar BDD em fluxos importantes de negócio e funcionalidades críticas.

O comportamento do sistema ficou mais claro utilizando cenários Gherkin.

No projeto LocalEats isso ajuda porque:
- melhora documentação viva
- reduz ambiguidades
- facilita entendimento dos requisitos
- melhora manutenção dos testes

BDD aproxima desenvolvimento, qualidade e negócio.
