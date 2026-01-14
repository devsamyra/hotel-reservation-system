_Este documento detalha os 20% de casos de uso considerados mais essenciais para o Sistema de Reserva de Hotéis, conforme solicitado na fase de Concepção do projeto._

---

### UC01: Fazer Reserva de Quarto

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC01 |
| **Nome** | Fazer Reserva de Quarto |
| **Atores Primários** | Hóspede |
| **Atores Secundários** | Sistema de Pagamento, Sistema de E-mail |
| **Descrição** | Este caso de uso permite que um Hóspede pesquise por quartos disponíveis, selecione uma opção, forneça seus dados e confirme a reserva mediante pagamento. |
| **Pré-condições** | 1. O Hóspede deve ter acesso à interface do sistema (web ou mobile).<br>2. O sistema deve ter a lista de quartos e suas disponibilidades atualizadas. |
| **Pós-condições** | 1. Uma nova reserva é criada no sistema com o status "Confirmada".<br>2. A disponibilidade do quarto selecionado é atualizada para "Reservado".<br>3. O Hóspede recebe um e-mail de confirmação com os detalhes da reserva. |

#### Fluxo Principal (Caminho Feliz)

1.  O Hóspede acessa a funcionalidade de "Buscar Quartos".
2.  O Hóspede informa as datas de check-in e check-out desejadas e o número de hóspedes.
3.  O Sistema exibe uma lista de tipos de quartos disponíveis para o período, com suas respectivas tarifas e detalhes.
4.  O Hóspede seleciona um tipo de quarto e clica em "Reservar".
5.  O Sistema apresenta um formulário para preenchimento dos dados pessoais do Hóspede (nome, e-mail, telefone).
6.  O Hóspede preenche e confirma seus dados.
7.  O Sistema redireciona para a etapa de pagamento, incluindo o caso de uso **UC02: Processar Pagamento**.
8.  Após a confirmação do pagamento, o Sistema cria a reserva.
9.  O Sistema atualiza a disponibilidade do quarto.
10. O Sistema dispara o envio de um e-mail de confirmação para o Hóspede (via **UC13: Enviar Notificação**).
11. O Sistema exibe uma mensagem de sucesso com o número da reserva.

#### Fluxos Alternativos

*   **A3a. Nenhum quarto disponível:** Se o Sistema não encontrar quartos disponíveis para as datas selecionadas, ele informa ao Hóspede e sugere a busca por novas datas.
*   **A6a. Hóspede já cadastrado:** Se o e-mail informado pelo Hóspede já existir na base, o sistema oferece a opção de fazer login para agilizar o preenchimento dos dados.

#### Fluxos de Exceção

*   **E1. Falha no processamento do pagamento:** Se o **UC02: Processar Pagamento** falhar, o sistema informa o erro ao Hóspede e permite que ele tente novamente com outra forma de pagamento. A reserva não é criada.
*   **E2. Sistema indisponível:** Se qualquer serviço externo (pagamento, e-mail) ou componente interno estiver indisponível, o sistema exibe uma mensagem de erro genérica e registra o incidente em log.

---

### UC02: Processar Pagamento

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC02 |
| **Nome** | Processar Pagamento |
| **Atores Primários** | Hóspede (inicia), Sistema (executa) |
| **Atores Secundários** | Sistema de Pagamento (Gateway Externo) |
| **Descrição** | Este caso de uso é responsável por coletar os dados de pagamento do Hóspede e processar a transação através de um gateway de pagamento externo. |
| **Pré-condições** | 1. O valor total da reserva deve ter sido calculado.<br>2. O Hóspede deve ter iniciado o processo de reserva (**UC01**). |
| **Pós-condições** | 1. A transação financeira é aprovada e registrada.<br>2. O status da reserva associada é atualizado para "Confirmada". |

#### Fluxo Principal (Caminho Feliz)

1.  O Sistema exibe as opções de pagamento (Cartão de Crédito, PIX).
2.  O Hóspede seleciona "Cartão de Crédito".
3.  O Sistema apresenta um formulário seguro para inserção dos dados do cartão (número, nome, validade, CVV).
4.  O Hóspede preenche e confirma os dados.
5.  O Sistema envia os dados da transação de forma segura para o **Sistema de Pagamento** externo.
6.  O **Sistema de Pagamento** valida os dados, autoriza a transação e retorna uma confirmação.
7.  O Sistema recebe a confirmação, registra o pagamento e finaliza o caso de uso com sucesso.

#### Fluxos Alternativos

*   **A2a. Pagamento com PIX:**
    1. O Hóspede seleciona "PIX".
    2. O Sistema gera um QR Code e um código "copia e cola" com validade de 10 minutos.
    3. O Sistema aguarda a confirmação de pagamento do **Sistema de Pagamento**.
    4. Ao receber a confirmação, o fluxo principal continua a partir do passo 7.

#### Fluxos de Exceção

*   **E1. Pagamento não autorizado:** Se o **Sistema de Pagamento** recusar a transação (limite insuficiente, dados inválidos), o fluxo é interrompido. O sistema informa o motivo da recusa ao Hóspede e permite uma nova tentativa.
*   **E2. Gateway de pagamento indisponível:** Se a comunicação com o **Sistema de Pagamento** falhar, o sistema informa ao Hóspede sobre a instabilidade e sugere tentar novamente mais tarde.

---

### UC03: Gerenciar Disponibilidade de Quartos

| Campo | Descrição |
| :--- | :--- |
| **ID** | UC03 |
| **Nome** | Gerenciar Disponibilidade de Quartos |
| **Atores Primários** | Gerente de Hotel |
| **Atores Secundários** | Sistema |
| **Descrição** | Este caso de uso permite que o Gerente de Hotel visualize o calendário de ocupação, bloqueie quartos para manutenção e ajuste manualmente o status de disponibilidade. |
| **Pré-condições** | 1. O Gerente de Hotel deve estar autenticado no sistema com as devidas permissões. |
| **Pós-condições** | 1. O status de disponibilidade de um ou mais quartos é atualizado no sistema. |

#### Fluxo Principal (Caminho Feliz)

1.  O Gerente acessa o painel de "Gestão de Quartos".
2.  O Sistema exibe um calendário ou uma lista com todos os quartos, mostrando o status de cada um (Disponível, Reservado, Ocupado, Em Manutenção) para um período selecionado.
3.  O Gerente seleciona um quarto e um intervalo de datas.
4.  O Gerente escolhe a opção "Bloquear para Manutenção".
5.  O Sistema solicita uma confirmação.
6.  O Gerente confirma a ação.
7.  O Sistema atualiza o status dos quartos selecionados para "Em Manutenção" no período informado, tornando-os indisponíveis para novas reservas.
8.  O Sistema exibe uma mensagem de sucesso.

#### Fluxos Alternativos

*   **A4a. Liberar quarto:** O Gerente seleciona um quarto que está "Em Manutenção" e escolhe a opção "Liberar Quarto". O sistema atualiza o status para "Disponível".
*   **A2a. Filtrar visualização:** O Gerente utiliza filtros para visualizar a disponibilidade por tipo de quarto, status ou andar.

#### Fluxos de Exceção

*   **E1. Tentativa de bloqueio de quarto reservado:** Se o Gerente tentar bloquear um quarto que já possui uma reserva confirmada no período, o sistema impede a ação e exibe uma mensagem de alerta com os detalhes da reserva conflitante.
