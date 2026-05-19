# Aula 10 — Testes Funcionais Automatizados – LocalEats

## 1. Fluxo funcional escolhido

### Fluxo escolhido
Login de usuário

### O que faz
Permite autenticar o usuário no sistema LocalEats.

### Problema que resolve
Garante acesso seguro às funcionalidades da plataforma.

### Importância
O login é um fluxo crítico porque controla o acesso do usuário ao sistema.

### Cenários esperados
- Login válido → sucesso
- Login inválido → mensagem de erro
- Campos vazios → validação

---

## 2. Teste automatizado com Codegen

### Comando utilizado

```bash
playwright codegen https://local-eats-unisenac.vercel.app/
```

### Fluxo gravado
- Acesso à página inicial
- Clique no botão Login
- Preenchimento de email
- Preenchimento de senha
- Clique no botão Entrar
- Verificação da mensagem de sucesso

### Código gerado inicialmente pelo Codegen

```python
from playwright.sync_api import Playwright, sync_playwright

def run(playwright: Playwright):
    browser = playwright.chromium.launch(headless=False)
    page = browser.new_page()
    page.goto("https://local-eats-unisenac.vercel.app/")
    page.get_by_text("Login").click()
    page.get_by_label("Email").fill("teste@email.com")
    page.get_by_label("Senha").fill("123456")
    page.get_by_text("Entrar").click()
    browser.close()

with sync_playwright() as playwright:
    run(playwright)
```

### Observações iniciais

#### O que o Codegen fez bem?
- Gerou rapidamente a navegação inicial
- Criou seletores automaticamente
- Facilitou o início da automação

#### O que gerou código desnecessário?
- Código repetitivo
- Estrutura pouco organizada
- Falta de reutilização
- Ausência de Page Object Model

---

## 3. Implementação do teste com Pytest

### Estrutura

```text
tests/
  test_login.py
```

### Código do teste

```python
def test_login_com_sucesso(page):
    page.goto("https://local-eats-unisenac.vercel.app/")

    page.get_by_text("Login").click()
    page.get_by_label("Email").fill("teste@email.com")
    page.get_by_label("Senha").fill("123456")
    page.get_by_text("Entrar").click()

    assert page.get_by_text("Bem-vindo").is_visible()
```

---

## 4. Refatoração com Page Object Model (POM)

### Estrutura

```text
pages/
  login_page.py

tests/
  test_login.py
```

### Classe LoginPage

```python
class LoginPage:
    def __init__(self, page):
        self.page = page

    def acessar(self):
        self.page.goto("https://local-eats-unisenac.vercel.app/")

    def realizar_login(self, email, senha):
        self.page.get_by_text("Login").click()
        self.page.get_by_label("Email").fill(email)
        self.page.get_by_label("Senha").fill(senha)
        self.page.get_by_text("Entrar").click()
```

### Teste utilizando POM

```python
from pages.login_page import LoginPage

def test_login(page):
    login = LoginPage(page)

    login.acessar()
    login.realizar_login(
        "teste@email.com",
        "123456"
    )

    assert page.get_by_text("Bem-vindo").is_visible()
```

---

## 5. Execução dos testes

### Comando executado

```bash
pytest
```

### Resultado

- Total de testes: 1
- Passaram: 1
- Falharam: 0

### Evidência

```bash
=====================
1 passed in 2.10s
=====================
```

---

## 6. Análise crítica dos testes

### O teste quebrou em algum momento?
Sim. O teste falhou inicialmente devido à mudança no texto do botão de login.

### Quais seletores foram mais difíceis?
Seletores baseados em texto foram mais frágeis porque pequenas alterações na interface quebravam o teste.

### O Codegen ajudou?
Sim. Ele acelerou a criação inicial do fluxo, mas gerou código pouco organizado.

### O teste é confiável?
Parcialmente. Ele funciona bem no cenário atual, mas ainda depende de elementos visuais específicos.

### O que tornaria o teste mais robusto?
- Uso de IDs específicos
- Seletores mais estáveis
- Melhor tratamento de espera
- Dados de teste controlados

### Quais são os riscos de manutenção?
Mudanças frequentes na interface podem quebrar os testes automatizados.

---

## 7. Reflexão no contexto do LocalEats

Testes automatizados não substituem totalmente testes manuais. Ambos são complementares.

Nem todos os fluxos precisam ser automatizados. Devem ser priorizados:
- fluxos críticos
- funcionalidades mais utilizadas
- processos repetitivos

Os testes automatizados ajudam o projeto do grupo porque:
- aumentam confiança nos deploys
- reduzem regressões
- aceleram validações
- melhoram a qualidade do sistema

A automação ajuda a equipe a detectar rapidamente problemas após mudanças no frontend.
