# Engenharia de Requisitos com GenAI

Repositório de documentação de engenharia de requisitos assistida por inteligência artificial generativa para o **Sistema de Gestão de Eventos** da empresa **Eventus**.

O sistema centraliza inscrições, controle de vagas, pagamentos, cancelamentos, listas de espera, certificados e gestão de eventos corporativos (congressos, workshops e eventos corporativos).

## Objetivo

Substituir o processo manual baseado em formulários on-line e planilhas eletrônicas por uma solução integrada que ofereça:

- Melhor experiência aos **participantes**
- Maior controle operacional aos **organizadores**
- Gestão financeira estruturada para a **equipe financeira**
- Acesso contextualizado para **palestrantes**

---

## Uso de GenAI no projeto

### Ferramenta de GenAI utilizada

Foi utilizado o **Cursor** (agente de IA integrado ao IDE), como apoio nas seguintes atividades:
- identificação de lacunas, ambiguidades e inconsistências entre artefatos;
- revisão cruzada de identificadores, rastreabilidade e coerência entre documentos.

### Como a IA apoiou a engenharia de requisitos
A IA ajudou a:
- transformar a elicitação em artefatos organizados de análise;
- identificar dúvidas, lacunas e regras de negócio implícitas;
- estruturar requisitos funcionais, requisitos não funcionais e regras de negócio;
- organizar a especificação com histórias de usuário, casos de uso, critérios de aceitação e fluxos;
- sugerir formatos mais claros para documentação, como identificadores rastreáveis, tabelas e checklists de aceitação;
- revisar a consistência entre contextos (CTX), ambiguidades (AIC), requisitos (RF/RNF), regras (RB) e especificação (HU/UC/CA/PF).

### Sugestões aproveitadas

- identificar as fontes da elicitação com códigos rastreáveis (CTX, AIC, RF, RB, RNF, HU, UC, CA, PF);
- adotar abordagem ágil com histórias de usuário e critérios de aceitação verificáveis;
- incluir AIC-05 (Notificações) e AIC-06 (Permissões de Acesso) para cobrir lacunas identificadas em CTX-08;
- complementar referências cruzadas entre requisitos, regras de negócio e requisitos não funcionais;

### Sugestões modificadas

- A sugestão de casos de uso detalhados com múltiplos fluxos alternativos foi mantida na análise, mas os **protótipos e fluxos** foram simplificados para diagramas do fluxo principal, alinhando-se a uma abordagem mais ágil e direta.
- Métricas quantitativas sugeridas para requisitos não funcionais (desempenho, disponibilidade, acessibilidade) foram mantidas como **propostas preliminares**, pois ainda não houve acordo com stakeholders.
- Soluções para lista de espera, reembolso, reserva de vaga, certificado, notificações e conflitos de horário foram convertidas em **questões abertas** (AIC-01 a AIC-06), em vez de regras definitivas inventadas pela IA.

### Sugestões descartadas

Foram descartadas funcionalidades inventadas. Também não foram adotados, nesta etapa, protótipos de alta fidelidade, diagramas UML formais extensos, modelo físico de dados e decisões de arquitetura, por serem prematuros diante das questões abertas.

### Por que estes artefatos foram escolhidos

- **Análise** (elicitação, ambiguidades, RF, RNF, RB) captura o entendimento do domínio, restrições e decisões pendentes antes da especificação detalhada.
- **Especificação** (histórias de usuário, casos de uso, critérios de aceitação, protótipos e fluxos) traduz a análise em comportamentos testáveis e jornadas compreensíveis para desenvolvimento e validação.

Histórias de usuário comunicam valor por stakeholder; casos de uso detalham interações complexas; critérios de aceitação tornam requisitos verificáveis; fluxos em diagrama representam as jornadas principais sem antecipar implementação visual. A rastreabilidade por identificadores garante auditabilidade — requisito central quando a IA propõe e o autor valida, sem substituir decisões de negócio.

---

## Estrutura do repositório

```
engenharia-requisitos-genai/
├── README.md
├── analise/                          # Levantamento e análise de requisitos
│   ├── elicitacao.md                 # Contextos do projeto (CTX-01 a CTX-08)
│   ├── duvidas-e-lacunas.md          # Ambiguidades e pontos a esclarecer (AIC-01 a AIC-06)
│   ├── requisitos-funcionais.md      # Requisitos funcionais (RF-01 a RF-17)
│   ├── requisitos-nao-funcionais.md  # Requisitos não funcionais (RNF-01 a RNF-07)
│   └── regras-de-negocio.md          # Regras de negócio (RB-01 a RB-08)
└── especificacao/                    # Especificação detalhada do sistema
    ├── historias-de-usuario.md       # Histórias de usuário (HU-01 a HU-16)
    ├── casos-de-uso.md               # Casos de uso (UC-01 a UC-13)
    ├── criterios-de-aceitacao.md     # Critérios de aceitação (CA-01 a CA-17)
    └── prototipos-e-fluxos.md        # Fluxos principais (PF-01 a PF-07)
```

## Como navegar

1. Comece por [`analise/elicitacao.md`](analise/elicitacao.md) para entender o contexto do projeto.
2. Consulte [`analise/duvidas-e-lacunas.md`](analise/duvidas-e-lacunas.md) para lacunas pendentes.
3. Revise os requisitos e regras em `analise/requisitos-funcionais.md`, `analise/requisitos-nao-funcionais.md` e `analise/regras-de-negocio.md`.
4. Avance para a especificação em `especificacao/`, iniciando pelas histórias de usuário e casos de uso.
