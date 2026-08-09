# Protótipos e Fluxos

> Fluxos principais derivados dos casos de uso (UC) e histórias de usuário (HU).

---

## PF-01 — Consulta e inscrição em evento

**Rastreabilidade:** UC-01, UC-02 | HU-01, HU-02

```mermaid
flowchart TD
    A[Consultar eventos disponíveis] --> B[Selecionar evento]
    B --> C[Visualizar detalhes]
    C --> D[Realizar inscrição]
    D --> E{Evento gratuito ou pago?}
    E -->|Gratuito| F[Confirmar inscrição]
    E -->|Pago| G[Registrar inscrição pendente de pagamento]
    G --> H[Confirmar pagamento - PF-04]
    F --> I[Emitir comprovante e notificar participante]
    H --> I
```

---

## PF-02 — Inscrição em workshops

**Rastreabilidade:** UC-03 | HU-03

```mermaid
flowchart TD
    A[Consultar workshops do evento] --> B[Selecionar workshop]
    B --> C[Verificar conflito de horário e vagas]
    C --> D[Confirmar inscrição no workshop]
    D --> E[Atualizar programação do participante]
```

---

## PF-03 — Cancelamento de inscrição

**Rastreabilidade:** UC-04 | HU-06

```mermaid
flowchart TD
    A[Consultar minhas inscrições] --> B[Selecionar inscrição]
    B --> C[Cancelar inscrição]
    C --> D[Libera vaga]
    D --> E[Notificar participante]
```

---

## PF-04 — Confirmação de pagamento

**Rastreabilidade:** UC-09 | HU-13

```mermaid
flowchart TD
    A[Consultar pagamentos pendentes] --> B[Selecionar inscrição]
    B --> C[Confirmar pagamento]
    C --> D[Atualizar status da inscrição]
    D --> E[Notificar participante]
```

---

## PF-05 — Gestão de eventos

**Rastreabilidade:** UC-07, UC-08 | HU-09, HU-10

```mermaid
flowchart TD
    A[Criar ou editar evento] --> B[Configurar vagas e regras]
    B --> C[Adicionar workshops e atividades]
    C --> D[Publicar evento]
    D --> E[Acompanhar inscrições em tempo real]
```

---

## PF-06 — Emissão de certificado

**Rastreabilidade:** UC-11 | HU-08

```mermaid
flowchart TD
    A[Consultar certificados disponíveis] --> B[Selecionar evento concluído]
    B --> C[Verificar condições de emissão]
    C --> D[Gerar e disponibilizar certificado]
```

---

## PF-07 — Consulta do palestrante

**Rastreabilidade:** UC-12, UC-13 | HU-15, HU-16

```mermaid
flowchart TD
    A[Consultar programação] --> B[Selecionar atividade]
    B --> C[Consultar participantes inscritos]
```
