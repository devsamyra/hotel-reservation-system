# Análise de Requisitos - Sistema de Reserva de Hotéis

## 1. Interessados (Stakeholders)

### Usuários Finais
- **Hóspedes**: Pessoas que desejam fazer reservas de hospedagem
- **Gerentes de Hotel**: Responsáveis pela administração das reservas e gerenciamento de quartos
- **Recepcionistas**: Funcionários que auxiliam na confirmação e gerenciamento de check-in/check-out
- **Administradores do Sistema**: Responsáveis pela manutenção e suporte técnico

### Partes Interessadas Internas
- **Equipe de Desenvolvimento**: Responsável pela implementação do sistema
- **Equipe de Testes**: Responsável pela validação do sistema
- **Gerente de Projeto**: Responsável pelo acompanhamento do projeto

### Partes Interessadas Externas
- **Proprietários do Hotel**: Interessados nos lucros e eficiência operacional
- **Órgãos Reguladores**: Conformidade com leis de proteção de dados

---

## 2. Objetivos Funcionais

Os objetivos funcionais descrevem o que o sistema deve fazer:

1. **Permitir que hóspedes façam reservas de quartos**: O sistema deve permitir que usuários registrados selecionem datas, tipo de quarto e confirmem a reserva.

2. **Gerenciar disponibilidade de quartos**: O sistema deve manter atualizado o status de disponibilidade de cada quarto (disponível, reservado, ocupado, em manutenção).

3. **Processar pagamentos**: O sistema deve aceitar diferentes formas de pagamento (cartão de crédito, débito, transferência bancária) e registrar transações.

4. **Gerar confirmações de reserva**: O sistema deve enviar confirmações por e-mail com detalhes da reserva (número de confirmação, datas, valor total).

5. **Permitir modificação de reservas**: Hóspedes devem poder alterar datas ou cancelar reservas dentro de prazos estabelecidos.

6. **Gerenciar check-in e check-out**: O sistema deve registrar entrada e saída de hóspedes, atualizar status de quartos e gerar faturas.

7. **Manter cadastro de hóspedes**: O sistema deve armazenar informações de contato, histórico de reservas e preferências dos hóspedes.

8. **Gerar relatórios de ocupação**: Gerentes devem poder consultar taxa de ocupação, receita por período e desempenho de quartos.

9. **Gerenciar tarifas e promoções**: O sistema deve permitir configuração de preços por tipo de quarto, datas sazonais e promoções especiais.

10. **Notificar sobre eventos importantes**: O sistema deve enviar lembretes de check-in, confirmações de cancelamento e ofertas especiais.

---

## 3. Objetivos Não-Funcionais

Os objetivos não-funcionais descrevem como o sistema deve se comportar:

### Desempenho
- O sistema deve responder a requisições de busca de disponibilidade em menos de 2 segundos
- Suportar até 1.000 usuários simultâneos sem degradação significativa de performance
- Tempo de carregamento de páginas não deve exceder 3 segundos

### Segurança
- Todas as transações financeiras devem ser criptografadas (SSL/TLS)
- Senhas devem ser armazenadas com hash seguro (bcrypt ou similar)
- Implementar autenticação de dois fatores (2FA) para contas de gerentes
- Conformidade com LGPD (Lei Geral de Proteção de Dados)
- Auditoria de todas as operações sensíveis (alteração de preços, cancelamentos)

### Confiabilidade
- Disponibilidade do sistema de 99,5% (máximo 3,6 horas de inatividade por mês)
- Backup automático de dados a cada 6 horas
- Recuperação de falhas em menos de 15 minutos
- Implementar redundância de servidores

### Usabilidade
- Interface intuitiva e responsiva (mobile-first)
- Suportar navegadores modernos (Chrome, Firefox, Safari, Edge)
- Acessibilidade WCAG 2.1 nível AA
- Disponível em português, inglês e espanhol

### Manutenibilidade
- Código bem documentado e seguindo padrões de desenvolvimento
- Arquitetura modular e escalável
- Facilitar adição de novos tipos de quartos e serviços
- Logs detalhados para diagnóstico de problemas

### Escalabilidade
- Arquitetura preparada para crescimento de 50% ao ano
- Suportar adição de múltiplas unidades de hotel
- Banco de dados otimizado para grandes volumes de dados

---

## 4. Casos de Uso Identificados

### Total de Casos de Uso: 15

#### Casos de Uso Principais (20% = 3 casos de uso)
1. **UC01 - Fazer Reserva de Quarto** (Essencial)
2. **UC02 - Processar Pagamento** (Essencial)
3. **UC03 - Gerenciar Disponibilidade de Quartos** (Essencial)

#### Casos de Uso Secundários
4. UC04 - Modificar Reserva
5. UC05 - Cancelar Reserva
6. UC06 - Realizar Check-in
7. UC07 - Realizar Check-out
8. UC08 - Consultar Histórico de Reservas
9. UC09 - Gerenciar Cadastro de Hóspede
10. UC10 - Gerar Relatório de Ocupação
11. UC11 - Configurar Tarifas
12. UC12 - Criar Promoção
13. UC13 - Enviar Notificação
14. UC14 - Gerar Fatura
15. UC15 - Gerenciar Usuários do Sistema

---

## 5. Atores do Sistema

| Ator | Descrição |
|------|-----------|
| **Hóspede** | Pessoa que faz reserva e utiliza os serviços do hotel |
| **Gerente de Hotel** | Responsável pela administração e gerenciamento operacional |
| **Recepcionista** | Auxilia no check-in, check-out e atendimento ao hóspede |
| **Administrador do Sistema** | Gerencia usuários, configurações e manutenção do sistema |
| **Sistema de Pagamento (Externo)** | Serviço externo para processamento de pagamentos |
| **Sistema de E-mail (Externo)** | Serviço externo para envio de notificações |

---

## 6. Diagrama de Contexto

```
┌─────────────────────────────────────────────────────────┐
│         Sistema de Reserva de Hotéis                    │
│                                                         │
│  ┌──────────────┐    ┌──────────────┐    ┌───────────┐ │
│  │   Hóspede    │    │  Gerente     │    │Recepcionista
│  │              │    │  de Hotel    │    │           │ │
│  └──────────────┘    └──────────────┘    └───────────┘ │
│         │                   │                    │      │
│         └───────────────────┼────────────────────┘      │
│                             │                          │
│                    ┌────────▼────────┐                 │
│                    │  Sistema de     │                 │
│                    │  Reserva de     │                 │
│                    │  Hotéis         │                 │
│                    └────────┬────────┘                 │
│                             │                          │
│         ┌───────────────────┼───────────────────┐      │
│         │                   │                   │      │
│    ┌────▼────┐         ┌────▼────┐        ┌────▼──┐   │
│    │ Banco de │         │ Sistema │        │Sistema│   │
│    │ Dados    │         │ Pagamento        │Email  │   │
│    └──────────┘         └─────────┘        └───────┘   │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

---

## 7. Matriz de Rastreabilidade

| ID | Caso de Uso | Ator Primário | Objetivo Funcional | Prioridade |
|----|-------------|---------------|-------------------|-----------|
| UC01 | Fazer Reserva | Hóspede | OF1, OF2 | Alta |
| UC02 | Processar Pagamento | Sistema Pagamento | OF3 | Alta |
| UC03 | Gerenciar Disponibilidade | Gerente | OF2 | Alta |
| UC04 | Modificar Reserva | Hóspede | OF5 | Média |
| UC05 | Cancelar Reserva | Hóspede | OF5 | Média |
| UC06 | Realizar Check-in | Recepcionista | OF6 | Alta |
| UC07 | Realizar Check-out | Recepcionista | OF6 | Alta |
| UC08 | Consultar Histórico | Hóspede | OF7 | Média |
| UC09 | Gerenciar Cadastro | Hóspede | OF7 | Média |
| UC10 | Gerar Relatório | Gerente | OF8 | Média |
| UC11 | Configurar Tarifas | Gerente | OF9 | Alta |
| UC12 | Criar Promoção | Gerente | OF9 | Média |
| UC13 | Enviar Notificação | Sistema | OF10 | Média |
| UC14 | Gerar Fatura | Sistema | OF6 | Alta |
| UC15 | Gerenciar Usuários | Administrador | - | Média |
