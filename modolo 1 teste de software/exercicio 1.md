# Relatório de Análise de Defeitos – Sistema PsicoCare

**Disciplina:** Teste de Software  
**Curso:** APONTI – Teste de Software  
**Módulo:** 01  
**Aula:** 01  
**Execução:** 01 – Atividade Avaliativa

---

# Introdução

O sistema **PsicoCare** é um software web utilizado para gerenciar pacientes, psicólogos, consultas e processos administrativos de uma clínica de psicologia. Durante a fase de testes foram identificados oito defeitos que comprometem o funcionamento do sistema, a experiência do usuário e a confiabilidade das informações.

Neste relatório, cada defeito será analisado considerando:

- Em qual fase do ciclo de desenvolvimento poderia ter sido identificado;
- Os impactos para o usuário e para o negócio;
- A relação com o custo de correção de bugs.

---

# Defeito 1 – Ficha de Anamnese

## Fase ideal para encontrar

O defeito deveria ser encontrado durante os **testes de integração** ou **testes de sistema**, verificando se os dados realmente são gravados no banco de dados após o cadastro.

## Impactos

### Para o usuário

- O cadastro do paciente é perdido.
- A recepcionista precisa cadastrar novamente.
- Pode ocorrer atraso ou cancelamento da consulta.

### Para o negócio

- Retrabalho da equipe.
- Perda de confiança no sistema.
- Insatisfação dos pacientes.

## Relação com o custo de correção

Se encontrado durante os testes, a correção possui baixo custo. Caso seja descoberto somente em produção, haverá necessidade de recuperar informações perdidas, aumentando significativamente o custo da correção.

---

# Defeito 2 – Agenda de Consultas

## Fase ideal para encontrar

Este defeito deveria ser identificado durante os **testes unitários** ou **testes de integração**, validando a regra de negócio responsável pelo agendamento.

## Impactos

### Para o usuário

- Dois pacientes podem ser agendados para o mesmo horário.
- A agenda do psicólogo fica inconsistente.

### Para o negócio

- Atrasos nos atendimentos.
- Insatisfação dos pacientes.
- Perda de credibilidade da clínica.

## Relação com o custo de correção

Como é uma falha de regra de negócio, deveria ser corrigida antes da implantação. Em produção, pode causar diversos problemas operacionais e aumentar muito o custo da correção.

---

# Defeito 3 – Cadastro do Psicólogo

## Fase ideal para encontrar

O defeito poderia ser encontrado durante os **testes de unidade** ou **testes de validação de entrada**, verificando se o formato do CRP é válido.

## Impactos

### Para o usuário

- Psicólogos podem ser cadastrados com informações incorretas.

### Para o negócio

- Riscos legais.
- Problemas com auditorias.
- Cadastro de profissionais inválidos.

## Relação com o custo de correção

A validação é simples de implementar. Porém, se descoberta apenas em produção, poderá exigir revisão de diversos cadastros e gerar problemas legais.

---

# Defeito 4 – Controle Financeiro

## Fase ideal para encontrar

Durante os **testes unitários** ou **testes de regra de negócio**, utilizando valores negativos como entrada.

## Impactos

### Para o usuário

- Valores financeiros incorretos.
- Relatórios inconsistentes.

### Para o negócio

- Erros contábeis.
- Prejuízos financeiros.
- Problemas fiscais.

## Relação com o custo de correção

Quanto mais tarde o erro for descoberto, maior será o retrabalho para corrigir registros financeiros já realizados.

---

# Defeito 5 – Controle de Estoque

## Fase ideal para encontrar

Nos **testes unitários** ou **testes de integração**, verificando se o sistema impede saídas maiores que o estoque disponível.

## Impactos

### Para o usuário

- Quantidade negativa de materiais.
- Controle incorreto do estoque.

### Para o negócio

- Compras desnecessárias.
- Falta de materiais.
- Perdas financeiras.

## Relação com o custo de correção

É um erro simples de validação, mas em produção pode causar prejuízos financeiros e comprometer o controle de estoque.

---

# Defeito 6 – Exclusão de Paciente

## Fase ideal para encontrar

Durante os **testes de integração**, **testes de banco de dados** ou **testes de sistema**, verificando a integridade referencial.

## Impactos

### Para o usuário

- Consultas permanecem sem paciente associado.
- Histórico inconsistente.

### Para o negócio

- Perda da integridade dos dados.
- Dificuldade para auditorias.
- Riscos relacionados ao prontuário do paciente.

## Relação com o custo de correção

Este é um defeito de alta gravidade. Em produção, exige correção manual dos dados e pode comprometer todo o histórico da clínica.

---

# Defeito 7 – Pesquisa de Pacientes

## Fase ideal para encontrar

Durante os **testes de usabilidade** ou **testes de aceitação**, verificando diferentes formas de pesquisa.

## Impactos

### Para o usuário

- Dificuldade para localizar pacientes.
- Perda de tempo.

### Para o negócio

- Redução da produtividade.
- Experiência negativa para os usuários.

## Relação com o custo de correção

Apesar da prioridade ser baixa, ainda representa custo adicional quando corrigido após o sistema estar em produção.

---

# Defeito 8 – Login

## Fase ideal para encontrar

Durante os **testes de segurança** ou **testes de sistema**, simulando diversas tentativas incorretas de autenticação.

## Impactos

### Para o usuário

- Dados pessoais ficam vulneráveis.

### Para o negócio

- Possibilidade de ataques por força bruta.
- Vazamento de informações.
- Penalidades relacionadas à LGPD.
- Perda de credibilidade da clínica.

## Relação com o custo de correção

Este é um dos defeitos mais críticos. Caso seja explorado em produção, os prejuízos financeiros, legais e de imagem podem ser extremamente elevados.

---

# Relação Geral com o Gráfico de Custo de Correção de Bugs

O gráfico clássico do custo de correção demonstra que quanto mais tarde um defeito é encontrado, maior será o investimento necessário para corrigi-lo.

| Fase do Desenvolvimento | Custo Relativo |
|--------------------------|----------------|
| Requisitos e Análise | 1x |
| Projeto (Design) | 2x a 5x |
| Codificação | 5x a 10x |
| Testes | 15x a 20x |
| Produção | 50x a 100x ou mais |

No sistema **PsicoCare**, todos os defeitos poderiam ter sido identificados antes da implantação por meio de testes adequados.

Os defeitos de **persistência de dados**, **agendamento**, **controle financeiro**, **estoque**, **integridade do banco** e **segurança** possuem alto impacto operacional e financeiro quando chegam ao ambiente de produção.

---

# Conclusão

A análise dos defeitos demonstra a importância da realização de testes durante todas as etapas do desenvolvimento de software. A identificação precoce de falhas reduz custos, evita retrabalho e aumenta a qualidade do produto entregue.

Além disso, defeitos relacionados à segurança, regras de negócio e integridade dos dados podem causar prejuízos financeiros, riscos legais e perda de confiança dos usuários. Por esse motivo, investir em testes de unidade, integração, sistema, segurança e usabilidade é fundamental para garantir a qualidade e a confiabilidade do sistema PsicoCare.
