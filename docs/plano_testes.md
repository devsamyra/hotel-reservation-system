# Plano de Testes - Sistema de Reserva de Hotéis

## 1. Introdução

Este documento apresenta o plano de testes para o Sistema de Reserva de Hotéis, desenvolvido como parte da disciplina de Prática Profissional em Análise e Desenvolvimento de Sistemas. O plano descreve a estratégia de testes, casos de teste, métricas de qualidade e resultados da execução dos testes.

## 2. Estratégia de Testes

A estratégia de testes adota uma abordagem de testes funcionais, focando na validação de cada caso de uso identificado durante a fase de concepção. Os testes serão executados em um ambiente de teste que simula o ambiente de produção.

### 2.1 Tipos de Testes

- **Testes Funcionais:** Validação de cada funcionalidade conforme os requisitos especificados
- **Testes de Usabilidade:** Avaliação da interface e experiência do usuário
- **Testes de Performance:** Validação de tempo de resposta e capacidade do sistema
- **Testes de Segurança:** Validação de autenticação e proteção de dados

## 3. Casos de Teste

### 3.1 UC01 - Fazer Reserva de Quarto

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT01.01 | Buscar hotel por localização | Usuário na home | 1. Inserir localização 2. Clicar em Buscar | Lista de hotéis exibida | ✅ Passou |
| CT01.02 | Selecionar datas válidas | Usuário vê lista de hotéis | 1. Selecionar check-in 2. Selecionar check-out | Datas selecionadas | ✅ Passou |
| CT01.03 | Validar datas (check-out > check-in) | Usuário com datas selecionadas | 1. Tentar selecionar check-out anterior a check-in | Mensagem de erro exibida | ✅ Passou |
| CT01.04 | Visualizar detalhes do quarto | Usuário com resultado de busca | 1. Clicar em hotel 2. Visualizar detalhes | Informações completas exibidas | ✅ Passou |
| CT01.05 | Adicionar quarto ao carrinho | Usuário vê detalhes do quarto | 1. Clicar em "Reservar" | Quarto adicionado ao carrinho | ✅ Passou |

### 3.2 UC02 - Processar Pagamento

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT02.01 | Visualizar resumo da reserva | Usuário com itens no carrinho | 1. Ir para checkout | Resumo exibido com total | ✅ Passou |
| CT02.02 | Inserir dados pessoais | Usuário no checkout | 1. Preencher nome, email, telefone | Dados salvos | ✅ Passou |
| CT02.03 | Validar email | Usuário preencheu dados | 1. Inserir email inválido | Mensagem de erro exibida | ✅ Passou |
| CT02.04 | Selecionar método de pagamento | Usuário com dados válidos | 1. Selecionar cartão de crédito | Método selecionado | ✅ Passou |
| CT02.05 | Processar pagamento com sucesso | Usuário com dados de pagamento | 1. Clicar em "Confirmar Pagamento" | Pagamento processado com sucesso | ✅ Passou |
| CT02.06 | Validar dados do cartão | Usuário preencheu dados de pagamento | 1. Inserir cartão inválido | Mensagem de erro exibida | ✅ Passou |

### 3.3 UC03 - Gerenciar Disponibilidade de Quartos

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT03.01 | Visualizar calendário de disponibilidade | Gerente logado | 1. Acessar painel de gerenciamento | Calendário exibido | ✅ Passou |
| CT03.02 | Marcar quarto como indisponível | Gerente vê calendário | 1. Selecionar data 2. Marcar como indisponível | Quarto marcado como indisponível | ✅ Passou |
| CT03.03 | Validar período de indisponibilidade | Gerente marcou período | 1. Tentar reservar nesse período | Quarto não aparece nos resultados | ✅ Passou |

### 3.4 UC04 - Visualizar Reservas

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT04.01 | Listar todas as reservas do usuário | Usuário logado com reservas | 1. Acessar "Minhas Reservas" | Lista de reservas exibida | ✅ Passou |
| CT04.02 | Visualizar detalhes da reserva | Usuário vê lista de reservas | 1. Clicar em reserva | Detalhes completos exibidos | ✅ Passou |

### 3.5 UC05 - Cancelar Reserva

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT05.01 | Cancelar reserva com prazo | Usuário com reserva futura | 1. Clicar em "Cancelar" | Reserva cancelada com reembolso | ✅ Passou |
| CT05.02 | Validar prazo de cancelamento | Usuário com reserva próxima | 1. Tentar cancelar com menos de 24h | Mensagem de aviso exibida | ✅ Passou |

### 3.6 UC06 - Gerar Relatório de Ocupação

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT06.01 | Gerar relatório mensal | Gerente logado | 1. Selecionar período 2. Gerar relatório | Relatório com dados de ocupação | ✅ Passou |
| CT06.02 | Exportar relatório em PDF | Gerente vê relatório | 1. Clicar em "Exportar PDF" | Arquivo PDF gerado | ✅ Passou |

### 3.7 UC07 - Filtrar Hotéis por Amenidades

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT07.01 | Filtrar por Wi-Fi | Usuário vê lista de hotéis | 1. Marcar filtro "Wi-Fi" | Apenas hotéis com Wi-Fi exibidos | ✅ Passou |
| CT07.02 | Filtrar por múltiplas amenidades | Usuário vê lista de hotéis | 1. Marcar "Piscina" e "Academia" | Hotéis com ambas amenidades exibidos | ✅ Passou |

### 3.8 UC08 - Aplicar Cupom de Desconto

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT08.01 | Aplicar cupom válido | Usuário no checkout | 1. Inserir código de cupom 2. Aplicar | Desconto aplicado ao total | ✅ Passou |
| CT08.02 | Validar cupom inválido | Usuário no checkout | 1. Inserir cupom inexistente | Mensagem de erro exibida | ✅ Passou |

### 3.9 UC09 - Avaliar Hotel

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT09.01 | Submeter avaliação com estrelas | Usuário com reserva concluída | 1. Selecionar 5 estrelas 2. Submeter | Avaliação registrada | ✅ Passou |
| CT09.02 | Submeter comentário de avaliação | Usuário preencheu estrelas | 1. Escrever comentário 2. Submeter | Comentário registrado | ✅ Passou |

### 3.10 UC10 - Gerenciar Perfil de Usuário

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT10.01 | Atualizar dados pessoais | Usuário logado | 1. Acessar perfil 2. Editar dados | Dados atualizados com sucesso | ✅ Passou |
| CT10.02 | Alterar senha | Usuário logado | 1. Acessar segurança 2. Alterar senha | Senha alterada com sucesso | ✅ Passou |

### 3.11 UC11 - Recuperar Senha

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT11.01 | Solicitar recuperação de senha | Usuário na tela de login | 1. Clicar em "Esqueci a senha" 2. Inserir email | Email de recuperação enviado | ✅ Passou |
| CT11.02 | Redefinir senha via link | Usuário recebeu email | 1. Clicar no link 2. Inserir nova senha | Senha redefinida com sucesso | ✅ Passou |

### 3.12 UC12 - Fazer Login

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT12.01 | Login com credenciais válidas | Usuário na tela de login | 1. Inserir email 2. Inserir senha 3. Clicar em Login | Usuário logado com sucesso | ✅ Passou |
| CT12.02 | Validar email inválido | Usuário na tela de login | 1. Inserir email inválido 2. Clicar em Login | Mensagem de erro exibida | ✅ Passou |
| CT12.03 | Validar senha incorreta | Usuário na tela de login | 1. Inserir email correto 2. Inserir senha incorreta | Mensagem de erro exibida | ✅ Passou |

### 3.13 UC13 - Fazer Logout

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT13.01 | Logout com sucesso | Usuário logado | 1. Clicar em "Logout" | Usuário deslogado e redirecionado | ✅ Passou |

### 3.14 UC14 - Registrar Novo Usuário

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT14.01 | Registrar com dados válidos | Usuário na tela de registro | 1. Preencher formulário 2. Clicar em Registrar | Usuário criado com sucesso | ✅ Passou |
| CT14.02 | Validar email duplicado | Usuário na tela de registro | 1. Inserir email já registrado | Mensagem de erro exibida | ✅ Passou |
| CT14.03 | Validar senha fraca | Usuário na tela de registro | 1. Inserir senha com menos de 6 caracteres | Mensagem de erro exibida | ✅ Passou |

### 3.15 UC15 - Visualizar Histórico de Transações

| ID | Descrição | Pré-Condição | Passos | Resultado Esperado | Status |
|----|-----------|--------------|--------|-------------------|--------|
| CT15.01 | Listar histórico de transações | Usuário logado | 1. Acessar "Histórico de Transações" | Lista de transações exibida | ✅ Passou |
| CT15.02 | Filtrar por período | Usuário vê histórico | 1. Selecionar período 2. Filtrar | Transações do período exibidas | ✅ Passou |

## 4. Métricas de Qualidade

### 4.1 Cobertura de Testes

- **Total de Casos de Uso:** 15
- **Casos de Teste Criados:** 35
- **Cobertura:** 100%

### 4.2 Taxa de Sucesso

- **Testes Executados:** 35
- **Testes Aprovados:** 35
- **Testes Falhados:** 0
- **Taxa de Sucesso:** 100%

### 4.3 Tempo Médio de Execução

- **Tempo Total de Testes:** 2 horas e 15 minutos
- **Tempo Médio por Caso de Teste:** 3,86 minutos

### 4.4 Defeitos Encontrados

- **Total de Defeitos:** 0
- **Defeitos Críticos:** 0
- **Defeitos Maiores:** 0
- **Defeitos Menores:** 0

## 5. Dados de Autenticação para Testes

### 5.1 Usuário Cliente

- **Email:** cliente@teste.com
- **Senha:** Teste123!
- **Perfil:** Cliente

### 5.2 Usuário Gerente

- **Email:** gerente@teste.com
- **Senha:** Teste123!
- **Perfil:** Gerente

### 5.3 Usuário Administrador

- **Email:** admin@teste.com
- **Senha:** Teste123!
- **Perfil:** Administrador

## 6. Conclusão

Os testes executados demonstram que o Sistema de Reserva de Hotéis atende a todos os requisitos funcionais especificados. Com uma taxa de sucesso de 100% e nenhum defeito encontrado, o sistema está pronto para a fase de transição e implantação.

## 7. Referências

[1] Sommerville, I. (2015). *Engenharia de Software*. 9ª edição. Pearson.

[2] Pressman, R. S. (2010). *Engenharia de Software: Uma Abordagem Profissional*. 7ª edição. McGraw-Hill.

[3] Kaner, C., Falk, J., & Nguyen, H. Q. (1999). *Testing Computer Software*. 2ª edição. John Wiley & Sons.
