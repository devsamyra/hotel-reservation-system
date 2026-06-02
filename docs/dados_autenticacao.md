# Dados de Autenticação para Testes

## Informações de Acesso à Aplicação

A aplicação estará disponível online por **duas semanas** a partir da data de entrega desta tarefa, conforme solicitado.

### URL de Acesso

**URL da Aplicação:** `https://hotelresv-jumkqfp8.manus.space`

## Usuários de Teste

### 1. Usuário Cliente (Hóspede)

| Campo | Valor |
|-------|-------|
| **Email** | cliente@teste.com |
| **Senha** | Teste123! |
| **Perfil** | Cliente/Hóspede |
| **Permissões** | Buscar hotéis, fazer reservas, visualizar reservas, cancelar reservas, avaliar hotéis, gerenciar perfil |

**Descrição:** Este usuário pode realizar todas as operações de um cliente final, incluindo busca de hotéis, realização de reservas, processamento de pagamento e gerenciamento de suas reservas.

### 2. Usuário Gerente

| Campo | Valor |
|-------|-------|
| **Email** | gerente@teste.com |
| **Senha** | Teste123! |
| **Perfil** | Gerente |
| **Permissões** | Gerenciar disponibilidade de quartos, gerar relatórios de ocupação, visualizar todas as reservas |

**Descrição:** Este usuário tem acesso às funcionalidades de gerenciamento, podendo controlar a disponibilidade de quartos, gerar relatórios e visualizar todas as reservas do hotel.

### 3. Usuário Administrador

| Campo | Valor |
|-------|-------|
| **Email** | admin@teste.com |
| **Senha** | Teste123! |
| **Perfil** | Administrador |
| **Permissões** | Acesso total ao sistema, gerenciamento de usuários, configurações do sistema |

**Descrição:** Este usuário tem acesso total ao sistema e pode realizar todas as operações administrativas.

## Instruções de Teste

### Para Testar como Cliente

1. Acesse a URL da aplicação
2. Clique em "Fazer Login" ou "Registrar"
3. Insira as credenciais do usuário cliente
4. Explore as funcionalidades de busca e reserva

### Para Testar como Gerente

1. Acesse a URL da aplicação
2. Faça login com as credenciais do gerente
3. Acesse o painel de gerenciamento
4. Teste as funcionalidades de gerenciamento de disponibilidade e relatórios

### Para Testar como Administrador

1. Acesse a URL da aplicação
2. Faça login com as credenciais do administrador
3. Acesse o painel administrativo
4. Teste as funcionalidades de administração do sistema

## Dados de Teste Adicionais

### Hotéis Disponíveis para Reserva

1. **Hotel Paulista Center** - São Paulo, SP
   - Preço: R$ 250,00 por noite
   - Avaliação: 4.2/5 (342 avaliações)
   - Amenidades: Wi-Fi, Estacionamento, Academia

2. **Copacabana Palace Hotel** - Rio de Janeiro, RJ
   - Preço: R$ 450,00 por noite
   - Avaliação: 4.6/5 (891 avaliações)
   - Amenidades: Wi-Fi, Piscina, Spa

3. **Hotel Recife Plaza** - Recife, PE
   - Preço: R$ 180,00 por noite
   - Avaliação: 3.9/5 (178 avaliações)
   - Amenidades: Wi-Fi, Café da Manhã, Estacionamento

### Cupons de Desconto Disponíveis

| Código | Desconto | Validade |
|--------|----------|----------|
| PRIMEIRACOMPRA | 10% | 30/06/2026 |
| DESCONTO15 | 15% | 30/06/2026 |
| VERAO2026 | 20% | 30/06/2026 |

## Período de Disponibilidade

- **Data de Início:** 06/04/2026
- **Data de Término:** 20/04/2026 (duas semanas)
- **Horário de Operação:** 24 horas por dia

## Suporte e Dúvidas

Em caso de dúvidas ou problemas durante os testes, entre em contato com a equipe de desenvolvimento através do Fórum Geral da disciplina.

## Observações Importantes

1. Os dados de teste são fictícios e destinados exclusivamente para fins de avaliação
2. Não realizar operações que possam comprometer a integridade dos dados
3. Após o período de duas semanas, a aplicação será desativada
4. Todos os dados de teste serão removidos após a conclusão da disciplina
