# Casos de Teste - Sistema de Login

## Objetivo

Documentar casos de teste funcionais para a funcionalidade de Login de um sistema, contemplando cenários de sucesso, falha e segurança.

---

# Estrutura do Caso de Teste

Cada caso de teste possui os seguintes campos:

- ID
- Título
- Pré-condições
- Passos
- Resultado esperado

---

# Cenários de Sucesso

## CT-001 - Login com sucesso usando credenciais válidas

### Pré-condições

- Estar na tela de login do sistema.
- Possuir um cadastro ativo.
- Usuário: **usuario_teste**
- Senha: **Senha@123**

### Passos

1. Preencher o campo **Usuário** com **usuario_teste**.
2. Preencher o campo **Senha** com **Senha@123**.
3. Clicar no botão **Entrar**.

### Resultado esperado

O sistema deve redirecionar para a tela inicial (Dashboard) e exibir o nome do usuário no canto superior direito.

---

## CT-002 - Login utilizando a tecla Enter

### Pré-condições

- Estar na tela de login.

### Passos

1. Informar usuário válido.
2. Informar senha válida.
3. Pressionar a tecla **Enter**.

### Resultado esperado

O sistema deve realizar o login normalmente.

---

## CT-003 - Máscara da senha

### Pré-condições

- Estar na tela de login.

### Passos

1. Clicar no campo Senha.
2. Digitar **Senha@123**.
3. Observar os caracteres.

### Resultado esperado

A senha deve aparecer mascarada (••••••••).

---

## CT-004 - Login com espaço antes do usuário

### Pré-condições

- Usuário cadastrado.

### Passos

1. Digitar **" usuario_teste"** (com espaço no início).
2. Digitar a senha correta.
3. Clicar em **Entrar**.

### Resultado esperado

O sistema deve ignorar o espaço em branco e realizar o login.

---

## CT-005 - Login com senha contendo caracteres especiais

### Pré-condições

- Usuário cadastrado.
- Senha: **Teste#2024**

### Passos

1. Informar o usuário.
2. Informar a senha **Teste#2024**.
3. Clicar em **Entrar**.

### Resultado esperado

O sistema deve aceitar caracteres especiais e realizar o login normalmente.

---

# Cenários de Falha

## CT-006 - Usuário correto e senha incorreta

### Pré-condições

- Usuário cadastrado.

### Passos

1. Informar **joao.silva**.
2. Informar **SenhaErrada123**.
3. Clicar em **Entrar**.

### Resultado esperado

O sistema deve exibir a mensagem:

**Usuário ou senha inválidos**

Não deve informar qual dos campos está incorreto.

---

## CT-007 - Usuário inexistente

### Pré-condições

Nenhuma.

### Passos

1. Informar **usuario_que_nao_existe**.
2. Informar qualquer senha.
3. Clicar em **Entrar**.

### Resultado esperado

O sistema deve exibir:

**Usuário ou senha inválidos**

O tempo de resposta deve ser inferior a 3 segundos.

---

## CT-008 - Campos obrigatórios vazios

### Pré-condições

Tela de login carregada.

### Passos

1. Deixar os dois campos vazios.
2. Clicar em **Entrar**.

### Resultado esperado

O sistema deve impedir o envio do formulário e exibir a mensagem:

**Preencha o campo de usuário e senha**

Os campos devem ser destacados em vermelho.

---

## CT-009 - Múltiplos cliques no botão Entrar

### Pré-condições

- Credenciais válidas.

### Passos

1. Informar usuário e senha.
2. Clicar rapidamente cinco vezes no botão **Entrar**.

### Resultado esperado

O sistema deve processar apenas uma solicitação.

O botão deve ficar desabilitado ou exibir um indicador de carregamento.

---

## CT-010 - Tentativa de SQL Injection

### Pré-condições

- Estar na tela de login.

### Passos

1. Informar no campo Usuário:

' OR '1'='1

2. Informar no campo Senha:

' OR '1'='1

3. Clicar em **Entrar**.

### Resultado esperado

O sistema deve bloquear o acesso e exibir apenas:

**Usuário ou senha inválidos**

Nenhuma mensagem técnica do banco de dados deve ser apresentada ao usuário.

---

# Resumo

## Erros comuns de iniciantes

- Criar casos de teste genéricos.
- Escrever vários passos em uma única ação.
- Esquecer as pré-condições.
- Testar apenas cenários de sucesso.
- Escrever resultados esperados sem objetividade.

---

## Boas práticas

- Criar casos de teste claros e objetivos.
- Escrever um passo por ação.
- Informar todas as pré-condições.
- Testar cenários positivos e negativos.
- Validar requisitos de segurança.
- Verificar a experiência do usuário.
- Testar entradas inválidas.
- Garantir mensagens de erro claras.
- Evitar duplicidade de casos.
- Documentar corretamente os resultados esperados.

---

# Conclusão

Os casos de teste documentados garantem uma melhor cobertura da funcionalidade de login, permitindo validar cenários de sucesso, falha, usabilidade e segurança.

A execução desses testes contribui para aumentar a qualidade do software e reduzir falhas antes da entrega ao usuário final.

---

# Autor

**Mario Marinho**

- Curso: Análise e Desenvolvimento de Sistemas
- Disciplina: Teste de Software (QA)
- Instituição: IMES / Aponti Academy
