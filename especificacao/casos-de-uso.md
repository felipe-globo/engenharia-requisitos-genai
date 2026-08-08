# Casos de Uso

> **Observação:** Os casos de uso abaixo descrevem as interações principais entre atores e o Sistema de Gestão de Eventos da Eventus, derivados dos requisitos funcionais da análise.

**Atores:** Participante, Organizador, Equipe Financeira, Palestrante

---

## UC-01 — Consultar Eventos Disponíveis

**Ator principal:** Participante  
**Rastreabilidade:** RF-01 | HU-01

**Pré-condições:**
- O participante está autenticado no sistema (ou em modo de consulta pública, conforme definição futura).

**Fluxo principal:**
1. O participante acessa a listagem de eventos disponíveis.
2. O sistema exibe os eventos com informações relevantes para inscrição (nome, data, local, vagas, modalidade gratuita/paga).
3. O participante pode filtrar ou buscar eventos.
4. O participante seleciona um evento para ver detalhes.

**Pós-condições:**
- O participante visualizou as informações necessárias para decidir sobre a inscrição.

---

## UC-02 — Realizar Inscrição em Evento

**Ator principal:** Participante  
**Rastreabilidade:** RF-02 | RB-01, RB-02, RB-03 | HU-02

**Pré-condições:**
- Existe um evento disponível para inscrição.
- O participante está autenticado.

**Fluxo principal:**
1. O participante seleciona um evento e solicita inscrição.
2. O sistema verifica a disponibilidade de vagas (RB-03).
3. O sistema identifica a modalidade do evento — gratuito ou pago (RB-01).
4. Se gratuito, o sistema confirma a inscrição imediatamente.
5. Se pago, o sistema registra a inscrição com status pendente de pagamento (RB-02).
6. O sistema gera comprovante de inscrição (RF-06) e envia notificação (RF-17).
7. O sistema atualiza a contagem de vagas.

**Fluxos alternativos:**

**2a. Evento sem vagas disponíveis:**
- O sistema informa que o evento está lotado.
- O participante pode entrar na lista de espera, se habilitada (UC-06).

**5a. Pagamento pendente de confirmação:**
- A inscrição permanece com status "Aguardando confirmação de pagamento" até ação da Equipe Financeira (UC-09).

**Pós-condições:**
- Inscrição registrada com status adequado (confirmada ou pendente).
- Vaga reservada ou participante incluído na lista de espera.

**Pontos em aberto:** AIC-02 ⚠️ (momento de reserva da vaga e tempo de expiração)

---

## UC-03 — Inscrever-se em Workshop

**Ator principal:** Participante  
**Rastreabilidade:** RF-03 | RB-07 | HU-03

**Pré-condições:**
- O participante está inscrito no evento principal ou em processo de inscrição.
- Existem workshops disponíveis vinculados ao evento.

**Fluxo principal:**
1. O participante visualiza os workshops disponíveis do evento.
2. O participante seleciona um ou mais workshops.
3. O sistema verifica conflitos de horário com inscrições existentes (RB-07).
4. O sistema verifica disponibilidade de vagas do workshop.
5. O sistema confirma a inscrição no workshop.

**Fluxos alternativos:**

**3a. Conflito de horários detectado:**
- O sistema aplica a regra de negócio definida para conflitos (bloquear, alertar ou permitir confirmação). ⚠️ AIC-03

**Pós-condições:**
- Inscrição no workshop registrada ou recusada conforme regras aplicáveis.

---

## UC-04 — Cancelar Inscrição

**Ator principal:** Participante  
**Rastreabilidade:** RF-07 | RB-04, RB-06 | HU-06

**Pré-condições:**
- O participante possui inscrição ativa em um evento que permite cancelamento (RB-04).

**Fluxo principal:**
1. O participante acessa suas inscrições (UC-05).
2. O participante seleciona a inscrição e solicita cancelamento.
3. O sistema verifica se o evento permite cancelamento (RB-04).
4. O sistema cancela a inscrição e libera a vaga.
5. Se aplicável, o sistema inicia processo de reembolso (UC-10).
6. O sistema notifica o participante sobre o cancelamento (RF-17).

**Fluxos alternativos:**

**3a. Evento não permite cancelamento:**
- O sistema informa que o cancelamento não está disponível para este evento.

**Pós-condições:**
- Inscrição cancelada; vaga liberada ou próximo da lista de espera convocado.

**Pontos em aberto:** AIC-01 ⚠️ (prazo, condições e valor de reembolso)

---

## UC-05 — Acompanhar Inscrições

**Ator principal:** Participante  
**Rastreabilidade:** RF-05 | HU-04

**Pré-condições:**
- O participante está autenticado.

**Fluxo principal:**
1. O participante acessa a área "Minhas Inscrições".
2. O sistema exibe todas as inscrições com seus status (confirmada, pendente pagamento, cancelada, lista de espera).
3. O participante seleciona uma inscrição para ver detalhes.

**Pós-condições:**
- O participante visualizou o status atualizado de suas inscrições.

---

## UC-06 — Gerenciar Lista de Espera

**Atores:** Participante, Organizador  
**Rastreabilidade:** RF-08 | RB-05 | HU-07, HU-12

**Pré-condições:**
- O evento ou atividade atingiu capacidade máxima e possui lista de espera habilitada (RB-05).

**Fluxo principal (Participante):**
1. O participante tenta se inscrever em evento lotado.
2. O sistema oferece entrada na lista de espera.
3. O participante confirma interesse.
4. O sistema registra o participante na lista de espera.

**Fluxo principal (Organizador):**
1. Uma vaga é liberada (cancelamento ou não confirmação de pagamento).
2. O sistema convoca o próximo participante da lista de espera. ⚠️ AIC-02
3. O participante convocado confirma ou recusa a vaga dentro do prazo definido.
4. Se confirmado, a inscrição é efetivada; se recusado ou expirado, convoca-se o próximo.

**Pós-condições:**
- Lista de espera atualizada; vaga ocupada ou mantida disponível.

**Pontos em aberto:** AIC-02 ⚠️ (critério de ordenação, convocação e confirmação)

---

## UC-07 — Criar e Gerenciar Evento

**Ator principal:** Organizador  
**Rastreabilidade:** RF-09 | RB-03, RB-04, RB-05 | HU-09

**Pré-condições:**
- O organizador está autenticado com perfil de organizador.

**Fluxo principal:**
1. O organizador acessa a área de gestão de eventos.
2. O organizador cria um novo evento informando dados básicos, capacidade de vagas (RB-03), modalidade gratuita/paga (RB-01), permissão de cancelamento (RB-04) e configuração de lista de espera (RB-05).
3. O organizador adiciona workshops e atividades vinculadas.
4. O sistema publica o evento para inscrições.

**Fluxos alternativos:**

**4a. Editar evento existente:**
- O organizador altera informações, vagas ou regras do evento.
- O sistema valida impacto em inscrições existentes.

**Pós-condições:**
- Evento criado ou atualizado e disponível conforme configuração.

---

## UC-08 — Acompanhar Inscrições em Tempo Real

**Ator principal:** Organizador  
**Rastreabilidade:** RF-10 | HU-10

**Pré-condições:**
- O organizador possui eventos cadastrados.

**Fluxo principal:**
1. O organizador acessa o painel de acompanhamento do evento.
2. O sistema exibe quantidade de inscritos, vagas disponíveis e status das inscrições em tempo real.
3. O organizador pode filtrar por status ou atividade.

**Pós-condições:**
- Organizador visualizou dados atualizados de inscrições.

---

## UC-09 — Registrar e Confirmar Pagamento

**Ator principal:** Equipe Financeira  
**Rastreabilidade:** RF-12 | RB-01, RB-02 | HU-13

**Pré-condições:**
- Existem inscrições com pagamento pendente de confirmação.

**Fluxo principal:**
1. A equipe financeira acessa a lista de pagamentos pendentes.
2. A equipe financeira registra ou confirma o pagamento recebido.
3. O sistema atualiza o status da inscrição para confirmada (RB-02).
4. O sistema reserva definitivamente a vaga e notifica o participante (RF-17).

**Fluxos alternativos:**

**2a. Pagamento não confirmado dentro do prazo:**
- O sistema cancela a inscrição pendente e libera a vaga. ⚠️ AIC-02

**Pós-condições:**
- Pagamento confirmado e inscrição validada, ou vaga liberada.

---

## UC-10 — Gerenciar Reembolso

**Ator principal:** Equipe Financeira  
**Rastreabilidade:** RF-13 | RB-06 | HU-14

**Pré-condições:**
- Existe inscrição cancelada em evento pago com direito a reembolso.

**Fluxo principal:**
1. A equipe financeira acessa solicitações de reembolso.
2. O sistema exibe condições aplicáveis ao evento (RB-06).
3. A equipe financeira processa o reembolso conforme regras.
4. O sistema registra o reembolso e notifica o participante.

**Pós-condições:**
- Reembolso processado ou recusado conforme condições do evento.

**Pontos em aberto:** AIC-01 ⚠️ (critérios, prazos e valores)

---

## UC-11 — Emitir Certificado

**Ator principal:** Participante  
**Rastreabilidade:** RF-14 | RB-08 | HU-08

**Pré-condições:**
- O evento foi realizado.
- O participante possui inscrição confirmada.

**Fluxo principal:**
1. O participante acessa a área de certificados.
2. O sistema verifica se o participante atende às condições de emissão (RB-08).
3. O sistema gera e disponibiliza o certificado para download.

**Fluxos alternativos:**

**2a. Presença não confirmada (se exigida):**
- O sistema informa que o certificado não está disponível e indica o motivo. ⚠️ AIC-04

**Pós-condições:**
- Certificado emitido ou solicitação recusada com justificativa.

---

## UC-12 — Consultar Programação (Palestrante)

**Ator principal:** Palestrante  
**Rastreabilidade:** RF-15 | HU-15

**Pré-condições:**
- O palestrante está vinculado a atividades em eventos.

**Fluxo principal:**
1. O palestrante acessa sua programação.
2. O sistema exibe atividades, horários e locais das apresentações vinculadas ao palestrante.

**Pós-condições:**
- Palestrante visualizou sua programação atualizada.

---

## UC-13 — Consultar Participantes das Atividades (Palestrante)

**Ator principal:** Palestrante  
**Rastreabilidade:** RF-16 | RNF-02, RNF-05 | HU-16

**Pré-condições:**
- O palestrante está vinculado a atividades com participantes inscritos.

**Fluxo principal:**
1. O palestrante seleciona uma atividade sob sua responsabilidade.
2. O sistema exibe a lista de participantes inscritos, respeitando permissões de acesso (RNF-05). ⚠️ AIC-06
3. O palestrante consulta as informações autorizadas para seu perfil (RNF-02).

**Pós-condições:**
- Palestrante visualizou informações permitidas dos participantes.
