# 🧪 Casos de Teste - Sistema de Login

## 📖 Objetivo

Este documento apresenta os **casos de teste funcionais** da funcionalidade de **Login**, contemplando cenários de sucesso, falha e segurança, garantindo que o sistema atenda aos requisitos funcionais e ofereça uma boa experiência ao usuário.

---

# 📑 Índice

- [Estrutura do Caso de Teste](#-estrutura-do-caso-de-teste)
- [Cenários de Sucesso](#-cenários-de-sucesso)
  - CT-001
  - CT-002
  - CT-003
  - CT-004
  - CT-005
- [Cenários de Falha](#-cenários-de-falha)
  - CT-006
  - CT-007
  - CT-008
  - CT-009
  - CT-010
- [Resumo](#-resumo)
- [Conclusão](#-conclusão)

---

# 📋 Estrutura do Caso de Teste

| Campo | Descrição |
|--------|-----------|
| **ID** | Identificação única do caso de teste. |
| **Título** | Nome do cenário de teste. |
| **Pré-condições** | Estado necessário antes da execução do teste. |
| **Passos** | Sequência de ações realizadas pelo testador. |
| **Resultado Esperado** | Comportamento esperado do sistema. |

---

# ✅ Cenários de Sucesso

## CT-001 - Login com credenciais válidas

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-001 |
| **Título** | Login com sucesso usando credenciais válidas |
| **Pré-condições** | Usuário cadastrado (**usuario_teste**) com senha **Senha@123**. |
| **Passos** | 1. Informar o usuário.<br>2. Informar a senha.<br>3. Clicar em **Entrar**. |
| **Resultado Esperado** | O sistema deve redirecionar para o Dashboard e exibir o nome do usuário logado. |

---

## CT-002 - Login utilizando a tecla Enter

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-002 |
| **Título** | Login utilizando a tecla Enter |
| **Pré-condições** | Estar na tela de login. |
| **Passos** | 1. Informar usuário válido.<br>2. Informar senha válida.<br>3. Pressionar **Enter**. |
| **Resultado Esperado** | O login deve ser realizado normalmente. |

---

## CT-003 - Máscara da senha

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-003 |
| **Título** | Verificar ocultação da senha |
| **Pré-condições** | Tela de login aberta. |
| **Passos** | 1. Selecionar o campo senha.<br>2. Digitar a senha.<br>3. Observar os caracteres. |
| **Resultado Esperado** | A senha deve permanecer oculta durante toda a digitação. |

---

## CT-004 - Espaço antes do usuário

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-004 |
| **Título** | Login com espaço antes do usuário |
| **Pré-condições** | Usuário cadastrado. |
| **Passos** | 1. Digitar um espaço antes do usuário.<br>2. Informar a senha correta.<br>3. Clicar em Entrar. |
| **Resultado Esperado** | O sistema deve ignorar espaços extras e realizar o login. |

---

## CT-005 - Senha com caracteres especiais

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-005 |
| **Título** | Login com senha contendo caracteres especiais |
| **Pré-condições** | Usuário cadastrado com senha **Teste#2024**. |
| **Passos** | 1. Informar usuário.<br>2. Informar senha.<br>3. Clicar em Entrar. |
| **Resultado Esperado** | O sistema deve aceitar caracteres especiais e autenticar o usuário. |

---

# ❌ Cenários de Falha

## CT-006 - Senha incorreta

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-006 |
| **Título** | Usuário válido e senha incorreta |
| **Pré-condições** | Usuário cadastrado. |
| **Passos** | 1. Informar usuário válido.<br>2. Informar senha incorreta.<br>3. Clicar em Entrar. |
| **Resultado Esperado** | Exibir a mensagem **"Usuário ou senha inválidos"**, sem informar qual campo está incorreto. |

---

## CT-007 - Usuário inexistente

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-007 |
| **Título** | Login com usuário inexistente |
| **Pré-condições** | Nenhuma. |
| **Passos** | 1. Informar um usuário inexistente.<br>2. Informar qualquer senha.<br>3. Clicar em Entrar. |
| **Resultado Esperado** | O sistema deve exibir **"Usuário ou senha inválidos"** em até 3 segundos. |

---

## CT-008 - Campos obrigatórios vazios

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-008 |
| **Título** | Campos obrigatórios vazios |
| **Pré-condições** | Tela de login carregada. |
| **Passos** | 1. Deixar usuário e senha vazios.<br>2. Clicar em Entrar. |
| **Resultado Esperado** | O sistema deve impedir o envio e destacar os campos obrigatórios. |

---

## CT-009 - Múltiplos cliques

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-009 |
| **Título** | Múltiplos cliques no botão Entrar |
| **Pré-condições** | Credenciais válidas. |
| **Passos** | 1. Informar usuário e senha.<br>2. Clicar rapidamente cinco vezes no botão Entrar. |
| **Resultado Esperado** | Apenas uma solicitação deve ser processada e o botão deve ser desabilitado durante o carregamento. |

---

## CT-010 - SQL Injection

| Campo | Descrição |
|--------|-----------|
| **ID** | CT-010 |
| **Título** | Tentativa de SQL Injection |
| **Pré-condições** | Estar na tela de login. |
| **Passos** | 1. Informar `' OR '1'='1` no usuário.<br>2. Informar `' OR '1'='1` na senha.<br>3. Clicar em Entrar. |
| **Resultado Esperado** | O sistema deve bloquear o acesso e exibir apenas **"Usuário ou senha inválidos"**, sem apresentar erros técnicos. |

---

# 📊 Resumo

## Erros comuns de iniciantes

| Erro | Correção |
|------|----------|
| Casos de teste genéricos | Descrever ações e resultados detalhadamente. |
| Vários passos em uma única linha | Separar cada ação em um passo. |
| Esquecer pré-condições | Informar o estado inicial do sistema. |
| Testar apenas cenários positivos | Incluir cenários negativos e alternativos. |
| Resultado esperado subjetivo | Informar exatamente o comportamento esperado. |

---

## Boas práticas de QA

| Boa prática | Benefício |
|-------------|-----------|
| Criar casos claros e objetivos | Facilita a execução dos testes. |
| Testar cenários positivos e negativos | Aumenta a cobertura dos testes. |
| Validar requisitos de segurança | Reduz vulnerabilidades. |
| Verificar a experiência do usuário | Melhora a usabilidade do sistema. |
| Documentar corretamente | Facilita manutenção e auditorias. |

---

# ✅ Conclusão

A documentação de casos de teste é essencial para garantir a qualidade do software. Os cenários apresentados cobrem situações de sucesso, falha e segurança, contribuindo para a identificação de problemas antes da entrega da aplicação ao usuário final.

---

# 👨‍💻 Autor

**Mario Marinho**

- **Curso:** Análise e Desenvolvimento de Sistemas
- **Disciplina:** Teste de Software (QA)
- **Instituição:** IMES / Aponti Academy
