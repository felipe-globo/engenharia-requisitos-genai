# Critérios de Aceitação

> **Observação:** Critérios derivados das histórias de usuário (HU) e requisitos funcionais (RF). Itens com ⚠️ dependem de definição pendente junto aos stakeholders (AIC).

---

## CA-01 — Consultar eventos disponíveis

**História:** HU-01 | **Requisito:** RF-01

- [ ] O sistema exibe listagem de todos os eventos disponíveis para inscrição.
- [ ] Cada evento exibe: nome, data, local, vagas disponíveis e modalidade (gratuito/pago).
- [ ] O participante consegue visualizar detalhes completos de um evento selecionado.
- [ ] Eventos esgotados são claramente identificados na listagem.

---

## CA-02 — Inscrição em evento gratuito

**História:** HU-02 | **Requisitos:** RF-02 | **Regras:** RB-01, RB-03

- [ ] Dado um evento gratuito com vagas disponíveis, quando o participante solicita inscrição, então a inscrição é confirmada imediatamente.
- [ ] O sistema decrementa a contagem de vagas disponíveis após confirmação.
- [ ] O sistema impede inscrição quando não há vagas (RB-03).

---

## CA-03 — Inscrição em evento pago

**História:** HU-02, HU-13 | **Requisitos:** RF-02, RF-12 | **Regras:** RB-01, RB-02

- [ ] Dado um evento pago, quando o participante solicita inscrição, então a inscrição é registrada com status "Aguardando confirmação de pagamento".
- [ ] A inscrição só é confirmada após confirmação da Equipe Financeira (RB-02).
- [ ] ⚠️ O momento em que a vaga é reservada durante pagamento pendente deve ser definido (AIC-02).

---

## CA-04 — Inscrição em workshop com conflito de horário

**História:** HU-03 | **Requisitos:** RF-03 | **Regra:** RB-07

- [ ] O participante consegue visualizar workshops disponíveis de um evento.
- [ ] O sistema detecta sobreposição de horários com inscrições existentes.
- [ ] ⚠️ O comportamento diante de conflito (bloquear, alertar ou permitir confirmação) deve ser definido (AIC-03).

---

## CA-05 — Acompanhar inscrições

**História:** HU-04 | **Requisito:** RF-05

- [ ] O participante visualiza todas as suas inscrições em uma única tela.
- [ ] Cada inscrição exibe status atual: confirmada, pendente pagamento, cancelada ou lista de espera.
- [ ] O participante consegue acessar detalhes de cada inscrição.

---

## CA-06 — Comprovante e notificação de inscrição

**História:** HU-05 | **Requisitos:** RF-06, RF-17

- [ ] Após inscrição confirmada, o sistema disponibiliza comprovante ao participante.
- [ ] O comprovante contém: identificação do participante, evento, data e status da inscrição.
- [ ] ⚠️ Canais e momentos de envio de notificação devem ser definidos (AIC-05).

---

## CA-07 — Cancelamento de inscrição

**História:** HU-06 | **Requisitos:** RF-07 | **Regras:** RB-04, RB-06

- [ ] Dado um evento que permite cancelamento, quando o participante solicita cancelamento, então a inscrição é cancelada e a vaga é liberada.
- [ ] Dado um evento que não permite cancelamento, quando o participante tenta cancelar, então o sistema exibe mensagem informando a indisponibilidade (RB-04).
- [ ] ⚠️ Prazo limite e condições de cancelamento devem ser definidos (AIC-01).

---

## CA-08 — Lista de espera

**História:** HU-07, HU-12 | **Requisitos:** RF-08 | **Regra:** RB-05

- [ ] Dado um evento lotado com lista de espera habilitada, quando o participante tenta se inscrever, então o sistema oferece entrada na lista de espera.
- [ ] Dado uma vaga liberada, quando o próximo da fila é convocado, então o participante é notificado.
- [ ] ⚠️ Critério de ordenação, convocação e prazo de confirmação devem ser definidos (AIC-02).

---

## CA-09 — Emissão de certificado

**História:** HU-08 | **Requisitos:** RF-14 | **Regra:** RB-08

- [ ] Dado um participante que atende às condições de emissão, quando solicita certificado, então o sistema gera e disponibiliza o documento.
- [ ] Dado um participante que não atende às condições, quando solicita certificado, então o sistema informa o motivo da indisponibilidade.
- [ ] ⚠️ Obrigatoriedade de confirmação de presença deve ser definida (AIC-04).

---

## CA-10 — Criação e gestão de eventos

**História:** HU-09 | **Requisito:** RF-09 | **Regras:** RB-03, RB-04, RB-05

- [ ] O organizador consegue criar evento informando nome, data, local, capacidade e modalidade de pagamento.
- [ ] O organizador consegue definir se o evento permite cancelamento (RB-04).
- [ ] O organizador consegue habilitar ou desabilitar lista de espera (RB-05).
- [ ] O organizador consegue adicionar workshops e atividades vinculadas ao evento.
- [ ] O organizador consegue editar eventos existentes sem perder rastreabilidade das inscrições.

---

## CA-11 — Acompanhamento de inscrições em tempo real

**História:** HU-10 | **Requisito:** RF-10

- [ ] O organizador visualiza quantidade total de inscritos por evento.
- [ ] O organizador visualiza vagas disponíveis e ocupadas em tempo real.
- [ ] O painel é atualizado automaticamente conforme novas inscrições ou cancelamentos.

---

## CA-12 — Gestão de participantes

**História:** HU-11 | **Requisito:** RF-11

- [ ] O organizador consegue listar todos os participantes inscritos em seus eventos.
- [ ] O organizador consegue filtrar participantes por evento, atividade ou status de inscrição.
- [ ] O organizador consegue visualizar detalhes de inscrição de cada participante.

---

## CA-13 — Gestão de lista de espera (Organizador)

**História:** HU-12 | **Requisito:** RF-08

- [ ] O organizador consegue visualizar a lista de espera de cada evento/atividade.
- [ ] O organizador consegue acompanhar posição e status de cada participante na fila.
- [ ] ⚠️ Ações manuais de convocação ou reordenação devem ser definidas (AIC-02).

---

## CA-14 — Confirmação de pagamento

**História:** HU-13 | **Requisito:** RF-12 | **Regras:** RB-01, RB-02

- [ ] A equipe financeira consegue listar inscrições com pagamento pendente.
- [ ] A equipe financeira consegue confirmar pagamento recebido, alterando status da inscrição para confirmada.
- [ ] Após confirmação, o participante é notificado e a vaga é definitivamente ocupada.

---

## CA-15 — Reembolso

**História:** HU-14 | **Requisito:** RF-13 | **Regra:** RB-06

- [ ] A equipe financeira consegue listar solicitações de reembolso pendentes.
- [ ] O sistema exibe condições de reembolso aplicáveis ao evento.
- [ ] A equipe financeira consegue registrar reembolso processado ou recusado.
- [ ] ⚠️ Critérios, prazos e valores de reembolso devem ser definidos (AIC-01).

---

## CA-16 — Consulta de programação (Palestrante)

**História:** HU-15 | **Requisito:** RF-15

- [ ] O palestrante visualiza todas as atividades em que está vinculado.
- [ ] Cada atividade exibe data, horário, local e evento correspondente.
- [ ] A programação é exibida em ordem cronológica.

---

## CA-17 — Consulta de participantes (Palestrante)

**História:** HU-16 | **Requisito:** RF-16 | **RNFs:** RNF-02, RNF-05

- [ ] O palestrante consegue listar participantes inscritos em suas atividades.
- [ ] O sistema exibe apenas informações autorizadas para o perfil de palestrante (RNF-05).
- [ ] Dados pessoais sensíveis são protegidos conforme política de privacidade (RNF-02).
- [ ] ⚠️ Escopo exato de dados visíveis ao palestrante deve ser definido (AIC-06).

---

## CA-NF — Critérios não funcionais (preliminares)

**Requisitos:** RNF-01 a RNF-07

- [ ] O acesso às funcionalidades respeita o perfil do usuário autenticado (RNF-01, RNF-05).
- [ ] Dados pessoais são exibidos somente a perfis autorizados (RNF-02).
- [ ] A contagem de vagas permanece consistente mesmo com inscrições simultâneas (RNF-07).
- [ ] ⚠️ Tempos de resposta, disponibilidade e padrões de acessibilidade devem ser quantificados (RNF-03, RNF-04, RNF-06).
