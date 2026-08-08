# Protótipos e Fluxos

> **Observação:** Descrições textuais de telas e fluxos derivados dos casos de uso (UC) e histórias de usuário (HU). Protótipos visuais de alta fidelidade deverão ser elaborados em etapa posterior.

---

## Perfis e áreas do sistema

| Perfil | Áreas principais |
|---|---|
| Participante | Eventos, Minhas Inscrições, Certificados |
| Organizador | Meus Eventos, Painel de Inscrições, Lista de Espera |
| Equipe Financeira | Pagamentos Pendentes, Reembolsos |
| Palestrante | Minha Programação, Participantes das Atividades |

---

## PF-01 — Fluxo de consulta e inscrição em evento

**Rastreabilidade:** UC-01, UC-02 | HU-01, HU-02 | PF-01

```mermaid
flowchart TD
    A[Participante acessa listagem de eventos] --> B{Evento selecionado}
    B --> C[Visualiza detalhes do evento]
    C --> D{Há vagas?}
    D -->|Sim| E{Evento gratuito ou pago?}
    D -->|Não| F{Lista de espera habilitada?}
    F -->|Sim| G[Entra na lista de espera]
    F -->|Não| H[Exibe evento lotado]
    E -->|Gratuito| I[Confirma inscrição]
    E -->|Pago| J[Registra inscrição pendente de pagamento]
    I --> K[Gera comprovante e notifica participante]
    J --> L[Aguarda confirmação financeira - UC-09]
    L --> K
    G --> M[Notifica posição na fila]
```

**Telas envolvidas:**
1. **Listagem de Eventos** — cards com nome, data, vagas e badge gratuito/pago/lotado.
2. **Detalhes do Evento** — descrição completa, programação de workshops, botão "Inscrever-se".
3. **Confirmação de Inscrição** — resumo da inscrição, status e link para comprovante.
4. **Lista de Espera** — confirmação de entrada na fila e posição estimada.

---

## PF-02 — Fluxo de inscrição em workshops

**Rastreabilidade:** UC-03 | HU-03 | RB-07

```mermaid
flowchart TD
    A[Participante acessa workshops do evento] --> B[Seleciona workshop]
    B --> C{Sobreposição de horário?}
    C -->|Não| D{Vagas disponíveis?}
    C -->|Sim| E[Aplica regra RB-07 - AIC-03 pendente]
    E --> F{Bloqueia / Alerta / Permite confirmação}
    F --> D
    D -->|Sim| G[Confirma inscrição no workshop]
    D -->|Não| H[Oferece lista de espera ou informa lotado]
    G --> I[Atualiza programação do participante]
```

**Telas envolvidas:**
1. **Grade de Workshops** — horários em grade visual; workshops inscritos destacados.
2. **Alerta de Conflito** — modal informando sobreposição e opções disponíveis. ⚠️ AIC-03

---

## PF-03 — Fluxo de cancelamento e reembolso

**Rastreabilidade:** UC-04, UC-10 | HU-06, HU-14 | RB-04, RB-06

```mermaid
flowchart TD
    A[Participante acessa Minhas Inscrições] --> B[Seleciona inscrição]
    B --> C{Evento permite cancelamento?}
    C -->|Não| D[Exibe mensagem de indisponibilidade]
    C -->|Sim| E[Solicita cancelamento]
    E --> F[Libera vaga]
    F --> G{Evento pago com direito a reembolso?}
    G -->|Sim| H[Encaminha para Equipe Financeira - UC-10]
    G -->|Não| I[Confirma cancelamento ao participante]
    H --> J[Financeiro processa reembolso - RB-06]
    J --> I
    F --> K[Convoca próximo da lista de espera - UC-06]
```

**Telas envolvidas:**
1. **Minhas Inscrições** — lista com status e ação "Cancelar" (quando disponível).
2. **Confirmação de Cancelamento** — resumo do impacto e informação sobre reembolso.
3. **Painel de Reembolsos (Financeiro)** — fila de solicitações pendentes.

---

## PF-04 — Fluxo de confirmação de pagamento

**Rastreabilidade:** UC-09 | HU-13 | RB-02

```mermaid
flowchart TD
    A[Financeiro acessa Pagamentos Pendentes] --> B[Seleciona inscrição]
    B --> C{Pagamento confirmado?}
    C -->|Sim| D[Atualiza status para Confirmada]
    D --> E[Reserva vaga definitivamente]
    E --> F[Notifica participante - RF-17]
    C -->|Não / Expirado| G[Cancela inscrição pendente]
    G --> H[Libera vaga]
    H --> I[Convoca lista de espera - UC-06]
```

**Telas envolvidas:**
1. **Pagamentos Pendentes** — tabela com participante, evento, valor e data limite.
2. **Detalhe do Pagamento** — botões "Confirmar" e "Recusar/Expirar".

---

## PF-05 — Fluxo de gestão de eventos (Organizador)

**Rastreabilidade:** UC-07, UC-08 | HU-09, HU-10

```mermaid
flowchart TD
    A[Organizador acessa Meus Eventos] --> B{Criar ou editar?}
    B -->|Criar| C[Preenche dados do evento]
    C --> D[Define vagas - RB-03]
    D --> E[Define modalidade pago/gratuito - RB-01]
    E --> F[Define cancelamento - RB-04]
    F --> G[Define lista de espera - RB-05]
    G --> H[Adiciona workshops/atividades]
    H --> I[Publica evento]
    B -->|Editar| J[Altera configurações existentes]
    J --> I
    I --> K[Painel de Inscrições em tempo real - UC-08]
```

**Telas envolvidas:**
1. **Formulário de Evento** — abas: Informações, Vagas e Regras, Programação.
2. **Painel de Inscrições** — gráficos e contadores de vagas ocupadas/disponíveis/lista de espera.

---

## PF-06 — Fluxo de emissão de certificado

**Rastreabilidade:** UC-11 | HU-08 | RB-08

```mermaid
flowchart TD
    A[Participante acessa Certificados] --> B[Seleciona evento concluído]
    B --> C{Atende condições RB-08?}
    C -->|Sim| D[Gera certificado]
    D --> E[Disponibiliza download]
    C -->|Não| F[Exibe motivo - ex.: presença não confirmada]
```

**Telas envolvidas:**
1. **Meus Certificados** — lista de eventos elegíveis com status de emissão.
2. **Visualização/Download** — preview do certificado em PDF.

---

## PF-07 — Fluxo do palestrante

**Rastreabilidade:** UC-12, UC-13 | HU-15, HU-16

```mermaid
flowchart TD
    A[Palestrante acessa Minha Programação] --> B[Visualiza atividades vinculadas]
    B --> C[Seleciona atividade]
    C --> D[Consulta participantes inscritos]
    D --> E{Sistema aplica RNF-05 - AIC-06}
    E --> F[Exibe dados autorizados para o perfil]
```

**Telas envolvidas:**
1. **Minha Programação** — agenda cronológica das apresentações.
2. **Participantes da Atividade** — lista filtrada conforme permissões do perfil. ⚠️ AIC-06

---

## Mapa de navegação simplificado

```mermaid
flowchart LR
    subgraph Participante
        P1[Eventos] --> P2[Detalhes]
        P2 --> P3[Inscrição]
        P1 --> P4[Minhas Inscrições]
        P4 --> P5[Certificados]
    end

    subgraph Organizador
        O1[Meus Eventos] --> O2[Formulário]
        O1 --> O3[Painel Inscrições]
        O3 --> O4[Lista de Espera]
    end

    subgraph Financeiro
        F1[Pagamentos] --> F2[Reembolsos]
    end

    subgraph Palestrante
        S1[Programação] --> S2[Participantes]
    end
```

---

## Pontos pendentes para prototipação

| ID | Descrição | Impacto nos fluxos |
|---|---|---|
| AIC-01 | Regras de cancelamento e reembolso | PF-03 |
| AIC-02 | Lista de espera e reserva de vagas | PF-01, PF-03, PF-04, PF-05 |
| AIC-03 | Conflitos de horários | PF-02 |
| AIC-04 | Certificados e presença | PF-06 |
| AIC-05 | Notificações | PF-01, PF-03, PF-04 |
| AIC-06 | Permissões de acesso | PF-07 |
