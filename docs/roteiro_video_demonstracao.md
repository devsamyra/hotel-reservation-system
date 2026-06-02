# Roteiro de Demonstração - Sistema de Reserva de Hotéis

## Informações do Vídeo

- **Duração:** 8 minutos
- **Resolução:** 1920x1080 (Full HD)
- **Taxa de Quadros:** 30 fps
- **Áudio:** Narração clara e fundo musical discreto
- **Objetivo:** Demonstrar todos os 15 casos de uso funcionando corretamente

## Estrutura do Vídeo

### Introdução (0:00 - 0:30)

**Narração:** "Bem-vindo ao Sistema de Reserva de Hotéis. Neste vídeo, vamos demonstrar todos os casos de uso implementados, mostrando como o sistema funciona de ponta a ponta."

**Visual:** Tela inicial da aplicação com logo e menu principal.

---

## Parte 1: Autenticação e Acesso (0:30 - 2:00)

### UC12 - Fazer Login (0:30 - 1:00)

**Narração:** "Começamos com o login. O usuário acessa a aplicação e insere suas credenciais."

**Passos:**
1. Mostrar tela de login
2. Inserir email: `cliente@teste.com`
3. Inserir senha: `Teste123!`
4. Clicar em "Fazer Login"
5. Mostrar redirecionamento para home

**Resultado Esperado:** Usuário logado com sucesso, acesso à home page.

### UC14 - Registrar Novo Usuário (1:00 - 1:30)

**Narração:** "Para novos usuários, existe a opção de registro. Vamos criar uma nova conta."

**Passos:**
1. Voltar à tela de login
2. Clicar em "Registrar"
3. Preencher formulário com:
   - Nome: João Silva
   - Email: joao@teste.com
   - Senha: Teste123!
   - Confirmar Senha: Teste123!
4. Clicar em "Registrar"
5. Mostrar mensagem de sucesso

**Resultado Esperado:** Novo usuário criado e redirecionado para login.

### UC11 - Recuperar Senha (1:30 - 2:00)

**Narração:** "Se o usuário esquecer sua senha, pode usar a opção de recuperação."

**Passos:**
1. Na tela de login, clicar em "Esqueci a Senha"
2. Inserir email: `cliente@teste.com`
3. Clicar em "Enviar Link de Recuperação"
4. Mostrar mensagem: "Email de recuperação enviado"

**Resultado Esperado:** Email de recuperação enviado com sucesso.

---

## Parte 2: Busca e Reserva (2:00 - 4:30)

### UC01 - Fazer Reserva de Quarto (2:00 - 3:30)

**Narração:** "Agora vamos fazer uma reserva. O usuário busca por hotéis em sua localização desejada."

**Passos:**
1. Na home, mostrar barra de busca
2. Inserir localização: "São Paulo"
3. Selecionar data de check-in: 15/04/2026
4. Selecionar data de check-out: 17/04/2026
5. Clicar em "Buscar"
6. Mostrar lista de hotéis com:
   - Hotel Paulista Center
   - Copacabana Palace Hotel
   - Hotel Recife Plaza
7. Clicar em "Hotel Paulista Center"
8. Mostrar detalhes do hotel:
   - Descrição
   - Fotos
   - Amenidades (Wi-Fi, Estacionamento, Academia)
   - Avaliações (4.2/5 - 342 avaliações)
   - Preço: R$ 250,00 por noite
9. Clicar em "Reservar"
10. Mostrar quarto adicionado ao carrinho

**Resultado Esperado:** Reserva adicionada ao carrinho com sucesso.

### UC07 - Filtrar Hotéis por Amenidades (3:30 - 4:00)

**Narração:** "O sistema também permite filtrar hotéis por amenidades específicas."

**Passos:**
1. Voltar à lista de resultados
2. Mostrar filtros disponíveis
3. Marcar filtro "Piscina"
4. Mostrar lista atualizada com apenas hotéis que têm piscina
5. Marcar também "Wi-Fi"
6. Mostrar lista com ambas amenidades

**Resultado Esperado:** Filtros funcionando corretamente.

### UC08 - Aplicar Cupom de Desconto (4:00 - 4:30)

**Narração:** "Na hora do checkout, o usuário pode aplicar cupons de desconto."

**Passos:**
1. Ir para o carrinho
2. Mostrar resumo da reserva
3. Campo de cupom de desconto
4. Inserir cupom: `PRIMEIRACOMPRA`
5. Clicar em "Aplicar"
6. Mostrar desconto de 10% aplicado
7. Mostrar novo total atualizado

**Resultado Esperado:** Cupom aplicado com sucesso e desconto refletido.

---

## Parte 3: Pagamento e Confirmação (4:30 - 5:30)

### UC02 - Processar Pagamento (4:30 - 5:30)

**Narração:** "Agora vamos processar o pagamento da reserva."

**Passos:**
1. Clicar em "Ir para Checkout"
2. Preencher dados pessoais:
   - Nome: João Silva
   - Email: joao@teste.com
   - Telefone: (11) 98765-4321
3. Selecionar método de pagamento: Cartão de Crédito
4. Preencher dados do cartão:
   - Número: 4111 1111 1111 1111
   - Validade: 12/25
   - CVV: 123
5. Clicar em "Confirmar Pagamento"
6. Mostrar mensagem: "Pagamento processado com sucesso!"
7. Mostrar confirmação da reserva com número de confirmação

**Resultado Esperado:** Pagamento processado e reserva confirmada.

---

## Parte 4: Gerenciamento de Reservas (5:30 - 6:30)

### UC04 - Visualizar Reservas (5:30 - 6:00)

**Narração:** "O usuário pode visualizar todas as suas reservas em um só lugar."

**Passos:**
1. Fazer logout e login novamente com `cliente@teste.com`
2. Clicar em "Minhas Reservas"
3. Mostrar lista de reservas com:
   - Hotel Paulista Center
   - Data: 15/04/2026 a 17/04/2026
   - Status: Confirmada
   - Preço: R$ 450,00 (com desconto)
4. Clicar em uma reserva para ver detalhes completos
5. Mostrar:
   - Informações do hotel
   - Datas
   - Número de hóspedes
   - Preço total
   - Número de confirmação

**Resultado Esperado:** Reservas exibidas corretamente.

### UC05 - Cancelar Reserva (6:00 - 6:30)

**Narração:** "Se necessário, o usuário pode cancelar uma reserva."

**Passos:**
1. Na lista de reservas, clicar em "Cancelar Reserva"
2. Mostrar aviso: "Você será reembolsado em até 5 dias úteis"
3. Confirmar cancelamento
4. Mostrar mensagem: "Reserva cancelada com sucesso"
5. Mostrar reserva com status "Cancelada"

**Resultado Esperado:** Reserva cancelada com sucesso.

---

## Parte 5: Funcionalidades Adicionais (6:30 - 7:30)

### UC09 - Avaliar Hotel (6:30 - 7:00)

**Narração:** "Após a estadia, o usuário pode avaliar o hotel."

**Passos:**
1. Ir para "Minhas Reservas"
2. Clicar em uma reserva concluída
3. Clicar em "Avaliar Hotel"
4. Selecionar 5 estrelas
5. Escrever comentário: "Excelente atendimento e limpeza impecável!"
6. Clicar em "Enviar Avaliação"
7. Mostrar mensagem: "Avaliação enviada com sucesso"

**Resultado Esperado:** Avaliação registrada.

### UC10 - Gerenciar Perfil de Usuário (7:00 - 7:30)

**Narração:** "O usuário pode gerenciar seu perfil e alterar suas informações."

**Passos:**
1. Clicar em "Meu Perfil"
2. Mostrar informações do usuário
3. Clicar em "Editar Perfil"
4. Alterar telefone: (11) 99999-9999
5. Clicar em "Salvar"
6. Mostrar mensagem: "Perfil atualizado com sucesso"
7. Clicar em "Alterar Senha"
8. Inserir senha atual: Teste123!
9. Inserir nova senha: NovaSenha123!
10. Confirmar nova senha: NovaSenha123!
11. Clicar em "Alterar"
12. Mostrar mensagem: "Senha alterada com sucesso"

**Resultado Esperado:** Perfil e senha atualizados.

---

## Parte 6: Funcionalidades de Gerenciamento (7:30 - 8:00)

### UC03 - Gerenciar Disponibilidade de Quartos (7:30 - 7:45)

**Narração:** "Gerentes podem controlar a disponibilidade de quartos."

**Passos:**
1. Fazer logout
2. Login com gerente: `gerente@teste.com` / `Teste123!`
3. Clicar em "Painel de Gerenciamento"
4. Mostrar calendário de disponibilidade
5. Selecionar data: 20/04/2026
6. Marcar como "Indisponível"
7. Mostrar confirmação

**Resultado Esperado:** Disponibilidade marcada corretamente.

### UC06 - Gerar Relatório de Ocupação (7:45 - 8:00)

**Narração:** "Gerentes também podem gerar relatórios de ocupação."

**Passos:**
1. Clicar em "Relatórios"
2. Selecionar período: Abril/2026
3. Clicar em "Gerar Relatório"
4. Mostrar relatório com:
   - Taxa de ocupação: 85%
   - Receita total: R$ 12.500,00
   - Número de reservas: 25
5. Clicar em "Exportar PDF"
6. Mostrar arquivo sendo baixado

**Resultado Esperado:** Relatório gerado e exportado com sucesso.

### UC15 - Visualizar Histórico de Transações (7:55 - 8:00)

**Narração:** "Por fim, usuários podem visualizar seu histórico de transações."

**Passos:**
1. Fazer logout e login como cliente
2. Clicar em "Histórico de Transações"
3. Mostrar lista com:
   - Transação: Reserva Hotel Paulista Center
   - Data: 06/04/2026
   - Valor: R$ 450,00
   - Status: Concluída
4. Clicar em transação para ver detalhes

**Resultado Esperado:** Histórico exibido corretamente.

---

## Encerramento (8:00)

**Narração:** "Isso conclui nossa demonstração do Sistema de Reserva de Hotéis. O sistema está funcionando perfeitamente, com todos os 15 casos de uso implementados e testados. Obrigado por assistir!"

**Visual:** Tela inicial da aplicação com menu principal.

---

## Notas Técnicas para Gravação

1. **Velocidade de Navegação:** Manter um ritmo constante, nem muito rápido nem muito lento
2. **Clareza de Áudio:** Narração clara e bem articulada
3. **Transições:** Usar transições suaves entre as diferentes seções
4. **Legendas:** Adicionar legendas em português para melhor compreensão
5. **Zoom:** Quando necessário, fazer zoom em elementos específicos para melhor visualização
6. **Cursor:** Destacar o cursor do mouse para indicar cliques
7. **Efeitos:** Usar efeitos sonoros discretos para ações importantes (cliques, confirmações)

## Requisitos de Acesso

- **URL da Aplicação:** https://hotelresv-jumkqfp8.manus.space
- **Usuário Cliente:** cliente@teste.com / Teste123!
- **Usuário Gerente:** gerente@teste.com / Teste123!
- **Navegador Recomendado:** Chrome ou Firefox em Full HD

## Duração Total: 8 minutos

Este roteiro foi desenvolvido para demonstrar de forma clara e objetiva todos os 15 casos de uso do Sistema de Reserva de Hotéis, permitindo que os avaliadores compreendam completamente a funcionalidade do sistema.
