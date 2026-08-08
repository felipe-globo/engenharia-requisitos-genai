# Regras de Negócio

## RB-01 — Modalidade de Pagamento do Evento

**Descrição:**
Um evento poderá ser classificado como gratuito ou pago.

**Rastreabilidade:**

- Contexto: CTX-05, CTX-07
- Ambiguidade/Ponto de esclarecimento: —
- Requisitos funcionais relacionados: RF-02, RF-12
- Stakeholder: Equipe Financeira / Organizador

---

## RB-02 — Confirmação de Pagamento

**Descrição:**
Quando um evento exigir pagamento, determinadas inscrições deverão ter seu pagamento confirmado antes de serem consideradas válidas, conforme a condição estabelecida para o evento.

**Rastreabilidade:**

- Contexto: CTX-05, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-02
- Requisitos funcionais relacionados: RF-02, RF-12
- Stakeholder: Equipe Financeira / Organizador

---

## RB-03 — Capacidade de Vagas

**Descrição:**
Cada evento ou atividade deverá possuir uma capacidade máxima de participantes, que deverá ser respeitada pelo processo de inscrição.

**Rastreabilidade:**

- Contexto: CTX-04, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-02
- Requisitos funcionais relacionados: RF-02, RF-04
- Stakeholder: Organizador

---

## RB-04 — Disponibilidade de Cancelamento

**Descrição:**
O cancelamento de uma inscrição deverá estar disponível somente para eventos que permitirem essa operação.

**Rastreabilidade:**

- Contexto: CTX-03, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-01
- Requisito funcional relacionado: RF-07
- Stakeholder: Organizador / Participante

---

## RB-05 — Lista de Espera

**Descrição:**
Eventos ou atividades que atingirem sua capacidade máxima poderão utilizar uma lista de espera para participantes interessados em uma eventual disponibilidade de vaga.

**Rastreabilidade:**

- Contexto: CTX-04, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-02
- Requisito funcional relacionado: RF-08
- Stakeholder: Organizador / Participante

**Observação:**
O critério de ordenação, ingresso, convocação e confirmação da lista de espera ainda precisa ser definido.

---

## RB-06 — Reembolso

**Descrição:**
O participante poderá ter direito a reembolso de acordo com as condições estabelecidas para o evento e para o cancelamento da inscrição.

**Rastreabilidade:**

- Contexto: CTX-05, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-01
- Requisitos funcionais relacionados: RF-07, RF-13
- Stakeholder: Equipe Financeira / Organizador

**Observação:**
Os critérios, prazos e valores de reembolso ainda precisam ser definidos.

---

## RB-07 — Conflito de Horários

**Descrição:**
As inscrições em atividades com horários conflitantes deverão seguir uma regra de negócio a ser definida pelos stakeholders.

**Rastreabilidade:**

- Contexto: CTX-03, CTX-04, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-03
- Requisito funcional relacionado: RF-03
- Stakeholder: Participante / Organizador

**Observação:**
Ainda não foi definido se o sistema deverá bloquear a inscrição, apresentar um alerta ou permitir a inscrição mediante confirmação do participante.

---

## RB-08 — Emissão de Certificado

**Descrição:**
O certificado deverá ser disponibilizado ao participante de acordo com as condições estabelecidas para sua emissão.

**Rastreabilidade:**

- Contexto: CTX-03, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-04
- Requisito funcional relacionado: RF-14
- Stakeholder: Participante / Organizador

**Observação:**
Ainda não foi definido se a confirmação de presença será obrigatória para a emissão do certificado.
