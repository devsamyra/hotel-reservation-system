# Documento de Elaboração do Projeto

## Sistema de Reserva de Hotéis

---

**Instituição:** Universidade Presbiteriana Mackenzie
**Disciplina:** Prática Profissional em Análise e Desenvolvimento de Sistemas
**Professor:** Tomaz Mikio Sasaki
**Data:** 14 de janeiro de 2026

---

## Sumário

1.  [Introdução](#1-introdução)
2.  [Informações Gerais do Projeto](#2-informações-gerais-do-projeto)
    1.  [Integrantes do Grupo](#21-integrantes-do-grupo)
    2.  [Links de Acesso](#22-links-de-acesso)
3.  [Análise de Requisitos (Revisão)](#3-análise-de-requisitos-revisão)
    1.  [Interessados (Stakeholders)](#31-interessados-stakeholders)
    2.  [Objetivos Funcionais](#32-objetivos-funcionais)
    3.  [Objetivos Não-Funcionais](#33-objetivos-não-funcionais)
4.  [Casos de Uso do Sistema (Revisão)](#4-casos-de-uso-do-sistema-revisão)
    1.  [Diagrama de Casos de Uso](#41-diagrama-de-casos-de-uso)
    2.  [Descrição Detalhada dos Casos de Uso Principais](#42-descrição-detalhada-dos-casos-de-uso-principais)
5.  [Protótipos de Tela](#5-protótipos-de-tela)
    1.  [Tela de Home/Busca](#51-tela-de-homebusca)
    2.  [Tela de Checkout/Pagamento](#52-tela-de-checkoutpagamento)
6.  [Modelo de Domínio](#6-modelo-de-domínio)
7.  [Diagramas de Classes de Projeto](#7-diagramas-de-classes-de-projeto)
8.  [Diagramas de Sequência de Projeto](#8-diagramas-de-sequência-de-projeto)
9.  [Referências](#9-referências)

---

### Lista de Figuras

*   Figura 1: Diagrama de Casos de Uso do Sistema de Reserva de Hotéis
*   Figura 2: Protótipo de Tela - Home/Busca
*   Figura 3: Protótipo de Tela - Checkout/Pagamento
*   Figura 4: Modelo de Domínio do Sistema de Reserva de Hotéis
*   Figura 5: Diagrama de Classes de Projeto do Sistema de Reserva de Hotéis
*   Figura 6: Diagrama de Sequência - Fazer Reserva e Processar Pagamento

### Lista de Tabelas

*   Tabela 1: Interessados do Sistema
*   Tabela 2: Detalhamento do Caso de Uso UC01
*   Tabela 3: Detalhamento do Caso de Uso UC02
*   Tabela 4: Detalhamento do Caso de Uso UC03

---

## 1. Introdução

Este documento apresenta a fase de **Elaboração** do projeto de desenvolvimento de um **Sistema de Reserva de Hotéis**, dando continuidade à fase de Concepção previamente documentada. O trabalho é realizado no âmbito da disciplina de Prática Profissional em Análise e Desenvolvimento de Sistemas e segue os princípios do Processo Unificado (PU), um modelo de desenvolvimento de software iterativo e incremental que organiza o ciclo de vida em quatro fases distintas: Concepção, Elaboração, Construção e Transição [1, 2].

Na fase de Elaboração, o foco é refinar a compreensão dos requisitos, estabelecer uma arquitetura robusta e desenvolver os modelos de design que servirão de base para a implementação. Esta entrega inclui protótipos de tela para as funcionalidades chave, um modelo de domínio abrangente, e diagramas de classes e de sequência para ilustrar a estrutura e o comportamento do sistema, conforme preconizado por metodologias de modelagem de software [3, 5].

---

## 2. Informações Gerais do Projeto

### 2.1. Integrantes do Grupo

*   Gabriela Refosco
*   Julio de Moura Stelzer
*   Lazaro Junior dos Santos
*   Samyra Driele Alborgueti

### 2.2. Links de Acesso

*   **URL do Repositório de Código-Fonte:** https://github.com/devsamyra/hotel-reservation-system
*   **URL do Quadro de Acompanhamento:** https://github.com/users/devsamyra/projects/1

---

## 3. Análise de Requisitos (Revisão)

Esta seção revisita e complementa a análise de requisitos realizada na fase de Concepção, garantindo que todos os aspectos funcionais e não-funcionais estejam alinhados com o detalhamento da fase de Elaboração.

### 3.1. Interessados (Stakeholders)

Os interessados, ou stakeholders, são todos os indivíduos ou grupos que são afetados pelo sistema ou que podem influenciar seu desenvolvimento. A identificação correta é crucial para o levantamento completo dos requisitos.

**Tabela 1: Interessados do Sistema**

| Categoria | Interessado | Descrição do Interesse |
| :--- | :--- | :--- |
| **Usuários Finais** | Hóspedes | Realizar reservas de forma rápida e segura, consultar informações e gerenciar suas estadias. |
| | Gerentes de Hotel | Otimizar a gestão de ocupação, maximizar a receita e obter relatórios estratégicos. |
| | Recepcionistas | Facilitar as operações de check-in e check-out, e ter acesso rápido às informações das reservas. |
| | Administradores | Garantir a estabilidade, segurança e manutenção contínua do sistema. |
| **Internos** | Equipe de Desenvolvimento | Construir um software de alta qualidade, manutenível e escalável. |
| **Externos** | Proprietários do Hotel | Aumentar a lucratividade, melhorar a eficiência operacional e a satisfação do cliente. |

### 3.2. Objetivos Funcionais

Os objetivos funcionais definem as capacidades e serviços que o sistema deve prover aos seus usuários.

*   **OF1:** Permitir que hóspedes pesquisem e realizem reservas de quartos online.
*   **OF2:** Gerenciar a disponibilidade de quartos em tempo real.
*   **OF3:** Processar pagamentos de forma segura através de múltiplos métodos.
*   **OF4:** Enviar notificações automáticas (confirmação, lembretes) por e-mail.
*   **OF5:** Permitir que hóspedes modifiquem ou cancelem suas reservas, sujeitos a regras de negócio.
*   **OF6:** Registrar as operações de check-in e check-out dos hóspedes.
*   **OF7:** Manter um cadastro centralizado de hóspedes e seu histórico.
*   **OF8:** Gerar relatórios gerenciais sobre ocupação, faturamento e outras métricas.
*   **OF9:** Permitir a configuração de tarifas, temporadas e promoções.

### 3.3. Objetivos Não-Funcionais

Os objetivos não-funcionais especificam critérios de qualidade e restrições operacionais do sistema.

*   **Desempenho:** O tempo de resposta para buscas de disponibilidade deve ser inferior a 2 segundos, mesmo com 1.000 usuários simultâneos.
*   **Segurança:** Aderência à LGPD, criptografia de dados sensíveis e transações financeiras, e armazenamento seguro de senhas.
*   **Confiabilidade:** O sistema deve ter uma disponibilidade de 99.5%, com rotinas de backup automáticas e um plano de recuperação de desastres.
*   **Usabilidade:** A interface deve ser intuitiva, responsiva (adaptável a dispositivos móveis) e acessível (WCAG 2.1 AA).

---

## 4. Casos de Uso do Sistema (Revisão)

Esta seção apresenta o diagrama de casos de uso e a descrição detalhada dos casos de uso principais, conforme definido na fase de Concepção.

### 4.1. Diagrama de Casos de Uso

O diagrama a seguir ilustra as principais interações entre os atores e os casos de uso identificados para o sistema.

**Figura 1: Diagrama de Casos de Uso do Sistema de Reserva de Hotéis**

![Diagrama de Casos de Uso](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL3VzZV9jYXNlX2RpYWdyYW0.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMM1Z6WlY5allYTmxYMlJwWVdkeVlXMC5wbmciLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=ID~Y8CKbEe-IkuWLJ8EHwls3QIzp3VBA0~oHiWCPWkU8~uxtXL15pHHJyAdyOvkWTJGA5jggLJrPgPOK9q-DSXzVC1IunLy2VFvHycibBumduIKHj7RkI6QDto6cDJWGOqO0Pjw5ZCtM6i3rLAR2c4yk6DG75uZn1hOdA-2GjJoOvOoyxJ6g6OvtS~bK1zZzTLUWRoC6-zvKbZef1LK9ZNRYmz7w13-GdblbpsdqWtTd8E~aQO~NfoFCuQpj87ev6ySmvKjPMK2bWJ2P6bi9Y2QYeRILxMdnMqVA~qfG4VFqutmY--Uh2cWQ4bNjMoA-JuaKIiMDtXOpAtVrZg5hbA__)

### 4.2. Descrição Detalhada dos Casos de Uso Principais

Este documento apresenta a especificação detalhada dos casos de uso priorizados como essenciais para a fase de Concepção do projeto. A seleção destes casos de uso, que representam o núcleo funcional do sistema, segue a recomendação de focar nos 20% de requisitos mais críticos durante as fases iniciais do Processo Unificado [4].

**Tabela 2: Detalhamento do Caso de Uso UC01**

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC01 |
| **Nome** | Fazer Reserva de Quarto |
| **Descrição** | Permite que um Hóspede pesquise por quartos, selecione uma opção e confirme a reserva mediante pagamento. |
| **Atores** | Hóspede (Primário), Sistema de Pagamento (Secundário) |
| **Fluxo Principal** | 1. Hóspede informa datas e busca quartos.<br>2. Sistema exibe opções disponíveis.<br>3. Hóspede seleciona quarto e informa dados pessoais.<br>4. Sistema invoca o **UC02: Processar Pagamento**.<br>5. Após sucesso, a reserva é criada, o quarto é marcado como indisponível e um e-mail de confirmação é enviado. |

**Tabela 3: Detalhamento do Caso de Uso UC02**

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC02 |
| **Nome** | Processar Pagamento |
| **Descrição** | Coleta os dados de pagamento e processa a transação através de um gateway externo. |
| **Atores** | Sistema (Primário), Sistema de Pagamento (Secundário) |
| **Fluxo Principal** | 1. Sistema exibe formulário seguro de pagamento.<br>2. Hóspede insere os dados do cartão de crédito ou seleciona PIX.<br>3. Sistema envia a transação para o gateway de pagamento.<br>4. Gateway autoriza a transação e retorna sucesso.<br>5. Sistema registra o pagamento e confirma a reserva. |

**Tabela 4: Detalhamento do Caso de Uso UC03**

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC03 |
| **Nome** | Gerenciar Disponibilidade de Quartos |
| **Descrição** | Permite que o Gerente de Hotel visualize a ocupação e bloqueie quartos para manutenção. |
| **Atores** | Gerente de Hotel (Primário) |
| **Fluxo Principal** | 1. Gerente acessa o painel de gestão de quartos.<br>2. Sistema exibe o calendário de ocupação.<br>3. Gerente seleciona um quarto e um período.<br>4. Gerente define o status como "Em Manutenção".<br>5. Sistema atualiza a disponibilidade, impedindo novas reservas no período. |

---

## 5. Protótipos de Tela

Esta seção apresenta os protótipos de alta fidelidade para as telas de Home/Busca e Checkout/Pagamento, ilustrando a interface do usuário e a experiência de interação com o sistema.

### 5.1. Tela de Home/Busca

**Figura 2: Protótipo de Tela - Home/Busca**

![Protótipo Home/Busca](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL3Byb3RvdGlwb19ob21lX2J1c2Nh.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMM0J5YjNSdmRHbHdiMTlvYjIxbFgySjFjMk5oLnBuZyIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTc5ODc2MTYwMH19fV19&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=dg3e4iDusTG1hgoG0HqbtFFFhO32bjxQ9w~98PeM2GWV6s9aD-uJmTBTvByh-Eu4rdqvIdVlLig2Izx-Vtpc7MA9K5dSZ4jcHhxUVXhQi1qdpLyainXWpubq1UkeY7vwNTE8Ty748u~HZyGOubfOH1WbdkYQir0I2gcT-OwyC-580pn8p-Ek7HUkcIg3WlJiwp7JAgHGi0ENpdkEpQN0N7yXEaKwwDdVwQr-upSazrrCwmsfCRB5O8mphfj7TGxQwxPGDC-P1kD6pf4MoCvHjXQ6ap8-GgElJN5xpfauoTJbdUf0q2jfqUw6QnsbpC9X2eg7GpHdPnzdwGH8evTyog__)

### 5.2. Tela de Checkout/Pagamento

**Figura 3: Protótipo de Tela - Checkout/Pagamento**

![Protótipo Checkout/Pagamento](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL3Byb3RvdGlwb19jaGVja291dF9wYWdhbWVudG8.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMM0J5YjNSdmRHbHdiMTlqYUdWamEyOTFkRjl3WVdkaGJXVnVkRzgucG5nIiwiQ29uZGl0aW9uIjp7IkRhdGVMZXNzVGhhbiI6eyJBV1M6RXBvY2hUaW1lIjoxNzk4NzYxNjAwfX19XX0_&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=YsMoQZ27xDGZzS~pkP9H~HIDRQ2uXCnDoGYD62GNc6DgqCyXfMEH3a2l0BqEfMXmfIZmI44ANh34DccXGLcZLbQa~j4HOu2RuGgcMIhemD6p~DakImqzXi6bS10Zg4gc~hhNuwoLUt0tunI8-uAK3E6g9QmmTxzY467wKuF~iwmykxEvsV7YE8kTnvGGnYNkECCeQPF2wIEe4trpsu0EHCQwbP9UE7-tbV7cHV~pkGB0r7VaDv72AHQLjssI3ayyhFlxiiS7tzYhOQaqijPd4iUM~~K~0A3MPcdIRr2~nCtWBYEPSNRjM91HKc5UzdyJypyEyUbAF1iRXMU84VCE~Q__)

---

## 6. Modelo de Domínio

O Modelo de Domínio representa as principais entidades de negócio do sistema e seus relacionamentos, fornecendo uma visão conceitual da estrutura de dados e do vocabulário do domínio. Este modelo é fundamental para garantir a consistência e a compreensão do sistema por toda a equipe de desenvolvimento.

**Figura 4: Modelo de Domínio do Sistema de Reserva de Hotéis**

![Modelo de Domínio](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL21vZGVsb19kb21pbmlv.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMMjF2WkdWc2IxOWtiMjFwYm1sdi5wbmciLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=iF3oXLtNEtHpmpkmtJQwbDWZebzI7hFIIF-F890xnkpjU8qJCmejzGPfs46b02XyusUwbDMKzbqXEt8IYvavaicWNlJLHT9yUY9VHBo9o37OKyTYWy8zaWioTWa3MFPNook72K0FepvbKxxjgZw52tJDN1X6UKFmXI8GyxNbraL4N3yWZDIQ0gZknIxutJU8Ss~PJxe9S7qVytaYQsW6Wa6XCP0kFdXJaIU3YlW8-lpaY0IdrOEbl1NCHzdevF6fKjl9ySpP5BC7MFrsaKeesNiG~OI6wRlJ692GM0L-FL4tMuDHTALjzppGyLMKxdrO~62OD3WkNLSj282i5VGlVg__)

---

## 7. Diagramas de Classes de Projeto

Os Diagramas de Classes de Projeto detalham a estrutura estática do sistema, mostrando as classes, seus atributos, métodos e os relacionamentos entre elas. Eles são essenciais para a fase de design, servindo como um blueprint para a implementação do código.

**Figura 5: Diagrama de Classes de Projeto do Sistema de Reserva de Hotéis**

![Diagrama de Classes](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL2RpYWdyYW1hX2NsYXNzZXM.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMMlJwWVdkeVlXMWhYMk5zWVhOelpYTS5wbmciLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=GarL45V-7DGjom-IuVqUaw2dNOZZWnbWOLTpYEhCsBnauYRTvS0aknMuFXSp4nf-ma9uXsFIvONfsjLEv8oLsN5QvSEKglzpX6RUAgLsjRRotoxLvRBJbrfiLobZbS7KGN975VpnsCLqLVWV09-OYGjta9gA1-cKic0NFKN4RH1lnbD91E7otLeOPmitHD4K43~BuM7n68gGtY3rHk3L4jiFH6JlA6~ItweRgxz1KjMcO4~AE1LchfQIkKBwT~tEvnXRhpA4GGowQA9xUp1Gv6KJrB0mLmizNUOt6Nt-8LvU5YbmAksbVd0or6gUrIqFLswDfM1jPMRi65dOv5hMhQ__)

---

## 8. Diagramas de Sequência de Projeto

Os Diagramas de Sequência ilustram a interação entre os objetos do sistema ao longo do tempo para a execução de um caso de uso específico. Eles são cruciais para entender o fluxo de mensagens e a colaboração entre os componentes, especialmente para os casos de uso mais críticos.

**Figura 6: Diagrama de Sequência - Fazer Reserva e Processar Pagamento**

![Diagrama de Sequência](https://private-us-east-1.manuscdn.com/sessionFile/suzfT09ThqFSrEUXinapWS/sandbox/1FV8tOWRp5eR4Asy5Q4JCn-images_1772844929894_na1fn_L2hvbWUvdWJ1bnR1L2hvdGVsLXJlc2VydmF0aW9uLXN5c3RlbS9kb2NzL2RpYWdyYW1hX3NlcXVlbmNpYQ.png?Policy=eyJTdGF0ZW1lbnQiOlt7IlJlc291cmNlIjoiaHR0cHM6Ly9wcml2YXRlLXVzLWVhc3QtMS5tYW51c2Nkbi5jb20vc2Vzc2lvbkZpbGUvc3V6ZlQwOVRocUZTckVVWGluYXBXUy9zYW5kYm94LzFGVjh0T1dScDVlUjRBc3k1UTRKQ24taW1hZ2VzXzE3NzI4NDQ5Mjk4OTRfbmExZm5fTDJodmJXVXZkV0oxYm5SMUwyaHZkR1ZzTFhKbGMyVnlkbUYwYVc5dUxYTjVjM1JsYlM5a2IyTnpMMlJwWVdkeVlXMWhYM05sY1hWbGJtTnBZUS5wbmciLCJDb25kaXRpb24iOnsiRGF0ZUxlc3NUaGFuIjp7IkFXUzpFcG9jaFRpbWUiOjE3OTg3NjE2MDB9fX1dfQ__&Key-Pair-Id=K2HSFNDJXOU9YS&Signature=qa3kTxXuCDC55dmAtRmLKO6UpFGKTZpC4nuZfYM1NCW0BQ8370Zz63Acn9ppDc~RpT5WKjNAxLne4c3pV5iKOrjQ3aesOwBN-hVfdadcgyHiya8c0sg9EAov7Pfmswrl0-NCMQfxmV3NnL2I5wCbyepmTMogsBy9V2eVyfMSJSnaufcVHhyVk2iDsSHBkzDSG9Wa5zm-UWDSF2cJrsP-KDqnMA8UVwZVjv6jBEu~FDmKc~9azUHwlRkZa6wq4f3wVIm6KI5o1QwW0ASqnDxWUqHgbjZlhHJzwYEDxi0GuPr1RTVE39rmcXVsLpspk07cMtI3OohzIu9ITyAAWbfuDQ__)

---

## 9. Referências

[1] JACOBSON, I.; BOOCH, G.; RUMBAUGH, J. **The Unified Software Development Process**. Reading: Addison-Wesley, 1999.

[2] SOMMERVILLE, I. **Engenharia de Software**. 9. ed. São Paulo: Pearson Prentice Hall, 2011.

[3] GOMAA, H. **Software Modeling and Design: UML, Use Cases, Patterns, and Software Architectures**. Cambridge: Cambridge University Press, 2011.

[4] KRUCHTEN, P. **The Rational Unified Process: An Introduction**. 3. ed. Reading: Addison-Wesley, 2003.

[5] LARMAN, C. **Utilizando UML e padrões**: uma introdução à análise e ao projeto orientados a objetos e desenvolvimento iterativo. 3. ed. Porto Alegre: Bookman, 2011.
