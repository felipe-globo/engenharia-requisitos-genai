# Requisitos Não Funcionais

> **Observação:** Os requisitos abaixo são preliminares. O documento de elicitação indica que segurança, desempenho, disponibilidade, acessibilidade e privacidade ainda não foram detalhados junto aos stakeholders. Portanto, os critérios quantitativos e níveis de qualidade deverão ser definidos posteriormente.

## RNF-01 — Segurança das Informações

**Descrição:**
O sistema deverá garantir a segurança das informações armazenadas e processadas, restringindo o acesso às funcionalidades e dados conforme o perfil do usuário.

**Rastreabilidade:**

- Contexto: CTX-08
- Ambiguidade/Ponto de esclarecimento: —
- Stakeholder: Equipe de TI / Organizadores

---

## RNF-02 — Privacidade dos Dados

**Descrição:**
O sistema deverá proteger os dados pessoais dos participantes e restringir sua visualização de acordo com as permissões definidas para cada perfil.

**Rastreabilidade:**

- Contexto: CTX-06, CTX-08
- Ambiguidade/Ponto de esclarecimento: AIC-06
- Requisito funcional relacionado: RF-16
- Stakeholder: Equipe de TI / Participantes / Palestrantes

---

## RNF-03 — Desempenho

**Descrição:**
O sistema deverá apresentar desempenho adequado durante as operações de consulta, inscrição e gerenciamento de eventos, inclusive em períodos de alta demanda.

**Rastreabilidade:**

- Contexto: CTX-08
- Ambiguidade/Ponto de esclarecimento: —
- Stakeholder: Participantes / Organizadores / Equipe de TI

**Observação:**
Os tempos máximos de resposta e a quantidade esperada de usuários simultâneos ainda precisam ser definidos.

---

## RNF-04 — Disponibilidade

**Descrição:**
O sistema deverá permanecer disponível para acesso aos participantes e organizadores durante os períodos necessários para consulta, inscrição e gerenciamento dos eventos.

**Rastreabilidade:**

- Contexto: CTX-08
- Ambiguidade/Ponto de esclarecimento: —
- Stakeholder: Participantes / Organizadores / Equipe de TI

**Observação:**
O percentual mínimo de disponibilidade e os períodos de manutenção ainda precisam ser definidos.

---

## RNF-05 — Controle de Acesso

**Descrição:**
O sistema deverá controlar o acesso às funcionalidades e informações de acordo com o perfil e as responsabilidades de cada usuário.

**Rastreabilidade:**

- Contexto: CTX-02, CTX-06, CTX-08
- Ambiguidade/Ponto de esclarecimento: AIC-06
- Requisito funcional relacionado: RF-16
- Stakeholder: Equipe de TI / Organizadores / Palestrantes

**Observação:**
As permissões específicas de cada perfil ainda precisam ser detalhadas.

---

## RNF-06 — Acessibilidade

**Descrição:**
O sistema deverá oferecer uma interface acessível aos usuários, considerando as necessidades de acessibilidade aplicáveis à solução.

**Rastreabilidade:**

- Contexto: CTX-08
- Ambiguidade/Ponto de esclarecimento: —
- Stakeholder: Participantes / Equipe de TI

**Observação:**
Os critérios e padrões de acessibilidade a serem adotados ainda precisam ser definidos.

---

## RNF-07 — Consistência do Controle de Vagas

**Descrição:**
O sistema deverá garantir a consistência das informações relacionadas à capacidade dos eventos e às inscrições, evitando que a quantidade de participantes confirmados ultrapasse a capacidade estabelecida.

**Rastreabilidade:**

- Contexto: CTX-04, CTX-05, CTX-07
- Ambiguidade/Ponto de esclarecimento: AIC-02
- Requisitos funcionais relacionados: RF-04, RF-08
- Regras de negócio relacionadas: RB-03, RB-05
- Stakeholder: Organizadores / Equipe Financeira / Equipe de TI
