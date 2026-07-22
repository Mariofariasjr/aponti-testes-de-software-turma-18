# Atividade Avaliativa - Testes Funcionais

## Sistema Fictício: Sistema de Gerenciamento de Pedidos (SGP)

### Objetivo

Analisar as funcionalidades do Sistema de Gerenciamento de Pedidos (SGP) e identificar quais testes pertencem aos níveis de:

- Testes Unitários
- Testes de Integração
- Testes de Sistema
- Testes de Aceitação

Além disso, justificar cada escolha com base no objetivo e no nível de teste.

---

# Funcionalidades do Sistema

O Sistema de Gerenciamento de Pedidos (SGP) possui as seguintes funcionalidades:

- Cadastro e autenticação de usuários;
- Consulta de produtos disponíveis;
- Adição e remoção de itens no carrinho;
- Cálculo automático do valor total do pedido;
- Finalização do pedido com confirmação.

Também possui integrações com:

- Banco de dados de produtos;
- Serviço de autenticação;
- Serviço de pedidos.

Regras de negócio:

- O pedido deve conter pelo menos um item;
- O valor total deve considerar quantidade e preço dos produtos;
- Usuários não autenticados não podem finalizar pedidos;
- Após a confirmação, o pedido não pode ser alterado.

---

# 1. Testes Unitários

## Objetivo

Verificar o funcionamento correto de pequenas partes do código (funções, métodos ou classes), de forma isolada.

| Funcionalidade | Justificativa |
|---------------|---------------|
| Cálculo do valor total do pedido | Validar se o cálculo considera corretamente quantidade × preço dos produtos. |
| Validação de pedido com pelo menos um item | Garantir que o sistema impeça pedidos vazios. |
| Adição de item ao carrinho | Confirmar que um item é inserido corretamente no carrinho. |
| Remoção de item do carrinho | Verificar se o item é removido corretamente sem afetar os demais. |
| Validação do usuário autenticado | Testar a lógica que verifica se o usuário está autenticado antes da finalização do pedido. |

### Justificativa

Os testes unitários analisam apenas uma função ou método específico, sem depender de banco de dados, APIs ou outros componentes externos.

---

# 2. Testes de Integração

## Objetivo

Validar a comunicação entre módulos internos e serviços externos.

| Integração | Justificativa |
|------------|---------------|
| Sistema ↔ Banco de Dados de Produtos | Verificar se os produtos cadastrados são carregados corretamente. |
| Sistema ↔ Serviço de Autenticação | Garantir que o login funcione corretamente utilizando o serviço externo. |
| Sistema ↔ Serviço de Pedidos | Validar o envio do pedido após a confirmação da compra. |
| Carrinho ↔ Banco de Produtos | Confirmar que os preços utilizados no cálculo são os mesmos cadastrados no banco. |

### Justificativa

Os testes de integração verificam se diferentes módulos conseguem trocar informações corretamente.

---

# 3. Testes de Sistema

## Objetivo

Validar o funcionamento completo do sistema como um usuário real utilizaria.

| Cenário | Resultado Esperado |
|---------|--------------------|
| Cadastro de novo usuário | Usuário cadastrado com sucesso. |
| Login | Usuário autenticado corretamente. |
| Consulta de produtos | Lista de produtos exibida corretamente. |
| Adicionar itens ao carrinho | Itens adicionados corretamente. |
| Remover itens | Itens removidos corretamente. |
| Cálculo do pedido | Valor total exibido corretamente. |
| Finalizar pedido | Pedido confirmado com sucesso. |
| Alterar pedido após confirmação | Sistema deve impedir alterações. |

### Justificativa

Os testes de sistema avaliam todas as funcionalidades funcionando juntas, simulando o ambiente real da aplicação.

---

# 4. Testes de Aceitação

## Objetivo

Validar se o sistema atende às necessidades do cliente e às regras de negócio.

| Regra de Negócio | Teste de Aceitação |
|------------------|--------------------|
| Pedido deve possuir pelo menos um item | O sistema deve impedir pedidos vazios. |
| Valor total deve considerar quantidade e preço | O total exibido deve estar correto. |
| Usuários não autenticados não podem finalizar pedidos | O sistema deve bloquear a finalização. |
| Pedido confirmado não pode ser alterado | Após a confirmação, nenhuma alteração deve ser permitida. |

### Justificativa

Os testes de aceitação verificam se o sistema atende aos requisitos definidos pelo cliente antes da entrega do software.

---

# Resumo dos Níveis de Teste

| Nível de Teste | O que verifica | Exemplo no SGP |
|----------------|----------------|----------------|
| Unitário | Funções e métodos isolados | Cálculo do valor total |
| Integração | Comunicação entre módulos e serviços | Integração com banco de dados e autenticação |
| Sistema | Funcionamento completo da aplicação | Fluxo completo de compra |
| Aceitação | Atendimento aos requisitos do cliente | Regras de negócio do pedido |

---

# Conclusão

Cada nível de teste possui um objetivo específico e é fundamental para garantir a qualidade do software.

- **Testes Unitários** asseguram que pequenas partes do código funcionem corretamente.
- **Testes de Integração** verificam a comunicação entre módulos e serviços.
- **Testes de Sistema** avaliam toda a aplicação em funcionamento.
- **Testes de Aceitação** confirmam que o sistema atende às necessidades do cliente e às regras de negócio.

A utilização conjunta desses testes reduz falhas, aumenta a confiabilidade da aplicação e garante uma melhor experiência para o usuário final.
