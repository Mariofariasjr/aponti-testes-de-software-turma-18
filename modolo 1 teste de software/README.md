# Atividade Avaliativa - Testes Não Funcionais

## Objetivo

Elaborar um checklist de testes não funcionais para o sistema fictício **PACO (Plataforma de Agendamento de Consultas)**, conforme apresentado no slide 25.

Os testes contemplam os seguintes aspectos:

- Performance
- Segurança
- Usabilidade
- Compatibilidade

Cada item informa o que será verificado durante os testes e o risco associado caso o requisito não seja atendido.

---

## Sistema Proposto

### PACO - Plataforma de Agendamento de Consultas

A PACO é um sistema web que permite aos usuários realizar o agendamento de consultas médicas de forma simples e segura, enquanto administradores gerenciam horários e atendimentos.

### Funcionalidades Principais

- Cadastro e autenticação de usuários;
- Consulta de especialidades e profissionais disponíveis;
- Agendamento, cancelamento e visualização de consultas;
- Notificações de confirmação do agendamento;
- Área administrativa para gestão de horários.

---

## Checklist de Testes Não Funcionais

| Categoria | O que será verificado | Risco associado |
|------------|-----------------------|-----------------|
| **Performance** | Verificar o tempo de carregamento da página inicial e da tela de login. | Lentidão pode fazer o usuário desistir de utilizar o sistema. |
| **Performance** | Verificar o tempo de resposta na pesquisa por médicos e especialidades. | A busca pode ficar lenta e prejudicar a experiência do usuário. |
| **Performance** | Testar o sistema com vários usuários acessando simultaneamente em horários de pico. | O sistema pode travar, ficar lento ou indisponível. |
| **Performance** | Verificar o tempo necessário para concluir um agendamento. | Falhas podem gerar agendamentos duplicados ou perda de dados. |
| **Segurança** | Confirmar que apenas usuários autenticados conseguem agendar consultas. | Usuários não autorizados podem acessar funcionalidades restritas. |
| **Segurança** | Validar que apenas administradores possuem acesso à área administrativa. | Alterações indevidas em horários e consultas. |
| **Segurança** | Verificar a proteção dos dados pessoais dos pacientes conforme boas práticas de segurança. | Vazamento de informações confidenciais. |
| **Segurança** | Testar tentativas repetidas de login com senha incorreta. | Possibilidade de ataques de força bruta. |
| **Usabilidade** | Avaliar se a interface é intuitiva e fácil de utilizar. | Usuários podem encontrar dificuldades para realizar tarefas. |
| **Usabilidade** | Verificar se as mensagens de erro, confirmação e cancelamento são claras. | O usuário pode interpretar incorretamente as informações apresentadas. |
| **Usabilidade** | Confirmar que o cancelamento de consultas respeita a regra de até 24 horas antes da consulta. | Cancelamentos podem ocorrer de forma incorreta. |
| **Usabilidade** | Avaliar a legibilidade dos textos, menus e botões. | Dificuldade de navegação e aumento de erros do usuário. |
| **Compatibilidade** | Testar o funcionamento nos navegadores Google Chrome, Mozilla Firefox e Microsoft Edge. | Algumas funcionalidades podem não funcionar corretamente em determinados navegadores. |
| **Compatibilidade** | Testar o sistema em computadores, tablets e smartphones. | Problemas de acesso em diferentes dispositivos. |
| **Compatibilidade** | Verificar a responsividade da interface em diferentes resoluções de tela. | Layout desconfigurado e perda de usabilidade. |
| **Compatibilidade** | Testar o funcionamento em diferentes sistemas operacionais (Windows, Android e iOS). | Comportamentos diferentes da aplicação entre plataformas. |

---

## Conclusão

Os testes não funcionais são fundamentais para garantir que o sistema PACO ofereça qualidade, segurança, desempenho e uma boa experiência aos usuários.

A realização desses testes permite identificar problemas relacionados ao desempenho, proteção de dados, facilidade de uso e compatibilidade com diferentes dispositivos e navegadores, tornando a plataforma mais confiável e preparada para uso em ambiente real.

---

## Autor

**Mario Marinho**

- Curso: Análise e Desenvolvimento de Sistemas
- Disciplina: Teste de Software (QA)
- Instituição: IMES / Aponti Academy
