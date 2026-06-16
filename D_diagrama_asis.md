# Diagrama AS-IS
## Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal

### Legenda de estilos

| Estilo do nó | Significado |
|---|---|
| Azul | Etapa frontstage — URA ou Atendente Humano Caixa |
| Verde | Ponto de entrada / autenticação bem-sucedida |
| Vermelho | Fail point crítico (★) |
| Amarelo | Desfecho intermediário — senha ausente ou sem resolução |
| Cinza | Nó de saída (⬡) — cidadão deixa o escopo da URA Caixa |
| Roxo | Ponto de bifurcação de intenção |
| `— backstage —` | Processo operacional invisível ao cidadão |
| `— suporte —` | Infraestrutura técnica/operacional da etapa |
| ⚠ FPN | Fail point N (referência cruzada com `C_blueprint_asis.md`) |
| ? | Ponto em aberto — requer validação empírica |

---

```mermaid
flowchart LR

    START(["Cidadão\ndisca 0800 726 0207"])

    subgraph UNIV ["Etapas Universais — todas as jornadas"]
        E1["ETAPA 1 — Conexão\nURA Caixa Cidadão\nAtende · reproduz locução\n— backstage: roteia chamada —\n— suporte: infraestrutura URA/0800 · telefonia —"]
        E2["ETAPA 2 — Identificação da intenção\nURA Caixa Cidadão\nApresenta menu · classifica intenção\n— backstage: classifica demanda · prepara fluxo —\n— suporte: lógica de menu · base de canais —"]
    end

    BIF{{"Intenção\nidentificada"}}

    subgraph AC ["Ramo A + C — Solicitar ou Renovar benefício"]
        AC1["Redirecionamento externo\nURA Caixa Cidadão\nOrienta canais MTE verbalmente\n— backstage: aplica regra de canal —\n— suporte: base de canais de destino atualizada —\n⚠ FP1 Canal errado · sem protocolo entregue\n⚠ FP10 Prazo perdido — cidadão fora da janela 7-120 dias não habilita"]
        ACout(["⬡ Saída — ecossistema MTE\n158 · App CTPS Digital\nSINE/SRTE · Portal Gov.br"])
    end

    subgraph B ["Ramo B — Consultar benefício já solicitado"]
        B1["AUTENTICAÇÃO\nURA Caixa Cidadão\nSolicita CPF/NIS + Senha Cidadão via DTMF\n— backstage: valida Senha na base Caixa · lógica antifraude —\n— suporte: Senha Cidadão · infraestrutura DTMF · lotérica —\n⚠ FP4 dependência de etapa presencial para senha"]

        B1OK(["Autenticado\nprossegue para consulta"])
        B1NS(["Sem senha cadastrada\norienta cadastro\nem lotérica ou agência"])
        B1BL(["★ FP3 CRÍTICO\nSenha bloqueada por tentativas DTMF\nDestino de desbloqueio INDETERMINADO ?"])

        B2["CONSULTA\nURA / Atendente Humano Caixa\nVerbaliza status · data prevista de crédito · valor\n— backstage: recupera dados via SISGR · origem MTE —\n— suporte: SISGR · integração Caixa-MTE ? · apps ecossistema —\n⚠ FP5 divergência de status entre sistemas\n⚠ FP6 janela de 67 dias invisível ao cidadão\n⚠ FP7 mensagens genéricas de erro\n⚠ FP8 falhas sistêmicas em lote\n⚠ FP11 confusão entre faixas de parcelas por nº de solicitação"]

        B3["ESCALONAMENTO — condicional\nAtendente Humano Caixa\nTransfere · informa status · orienta canais externos\n— backstage: limite de alçada Caixa quando depende do MTE —\n— suporte: 158 · agência · Reclame Aqui · Ouvidoria MTE —\n⚠ FP2 queda de ligação sem callback\n⚠ FP9 empurra-empurra Caixa-MTE"]

        Bout(["⬡ Saída — ecossistema externo\n158 · Agência · Reclame Aqui\nOuvidoria MTE · Procon · Defensoria"])
    end

    subgraph D ["Ramo D — Registrar reclamação formal"]
        D1["ACOLHIMENTO + REGISTRO\nURA / Atendente Humano Caixa\nAcolhe narrativa · gera protocolo\n— backstage: gestão institucional de reclamações —\n— suporte: 0800 · infraestrutura de protocolo · Reclame Aqui —\nsem promessa de prazo ou retorno proativo confirmada"]

        D2["ENCAMINHAMENTO\nAtendente / Backstage Caixa\nOrienta canais de acompanhamento\nRoteia internamente a manifestação\n— suporte: Reclame Aqui · Ouvidoria MTE —\n⚠ FP9 empurra-empurra Caixa-MTE"]

        Dout(["⬡ Saída — canais externos\nReclame Aqui · Ouvidoria MTE\nProcon · Defensoria"])
    end

    START --> E1 --> E2 --> BIF

    BIF -->|"Solicitar ou renovar\n(1ª solicitação ou renovação)"| AC1
    AC1 --> ACout

    BIF -->|"Consultar\nbenefício"| B1
    B1 --> B1OK --> B2 --> B3 --> Bout
    B1 --> B1NS
    B1 --> B1BL

    BIF -->|"Reclamar\nformalmente"| D1
    D1 --> D2 --> Dout

    classDef ura fill:#dbeafe,stroke:#1d4ed8,color:#1e3a5f
    classDef critical fill:#fee2e2,stroke:#dc2626,color:#7f1d1d
    classDef exitnode fill:#f3f4f6,stroke:#9ca3af,color:#374151
    classDef startnode fill:#dcfce7,stroke:#15803d,color:#14532d
    classDef bifnode fill:#fdf4ff,stroke:#7c3aed,color:#4c1d95
    classDef oknode fill:#d1fae5,stroke:#059669,color:#064e3b
    classDef warnnode fill:#fef9c3,stroke:#ca8a04,color:#713f12

    class E1,E2,AC1,B1,B2,B3,D1,D2 ura
    class B1BL critical
    class ACout,Bout,Dout exit
    class ACout,Bout,Dout,B1NS exitnode
    class START startnode
    class BIF bifnode
    class B1OK oknode
    class B1NS warnnode
```

---

### Relações estruturais destacadas pelo diagrama

| Relação | O que o diagrama torna visível |
|---|---|
| **URA como ator único nas etapas universais** | As duas etapas de entrada são inteiramente operadas pela URA — o atendente humano só aparece a partir do Ramo B (consulta) e Ramo D (reclamação) |
| **Canal errado como fail point de entrada** | O Ramo A+C termina imediatamente em saída — a URA não tem capacidade resolutiva para a intenção mais frequente (solicitar o benefício) |
| **Autenticação como gargalo do Ramo B** | O nó de autenticação se ramifica em três saídas, uma delas crítica e com destino indeterminado — qualquer problema aqui bloqueia todo o ramo B |
| **Concentração de fail points na consulta** | Quatro fail points (FP5, FP6, FP7, FP8) se acumulam em uma única etapa — a consulta é o maior núcleo de risco do canal após a autenticação |
| **Escalonamento como antecâmara de saída** | O escalonamento não resolve — é estruturalmente uma transição para saída do canal, com risco adicional de queda de chamada antes de completar essa transição |
| **Backstage MTE como origem invisível** | Os dados verbalizados na consulta têm origem MTE (SISGR), mas a integração tem mecanismo indeterminado — a divergência de status (FP5) é sistêmica, não acidental |
| **Saídas sem protocolo nos Ramos A+C** | Ao contrário do Ramo D (que gera protocolo), os cidadãos redirecionados nos Ramos A e C saem sem nenhum artefato de continuidade |

---

### Tabela RACI — Responsabilidades e interações entre atores

> **Referência cruzada:** esta tabela também está disponível em `C_blueprint_asis.md` — seção "Tabela RACI", consolidada com os demais elementos do blueprint.

**Legenda:** R = Responsável (executa) · A = Aprovador/Autoridade (responde pelo resultado) · C = Consultado (fornece informação) · I = Informado (recebe o resultado)

| Etapa / Atividade | Cidadão | URA Caixa Cidadão | Atendente Humano Caixa | Backstage Caixa | MTE (externo) |
|---|---|---|---|---|---|
| **E1 — Atender a chamada e reproduzir locução** | I | **R/A** | — | I *(roteamento)* | — |
| **E2 — Apresentar menu e classificar intenção** | R *(seleciona opção)* | **R/A** | — | R *(classifica demanda)* | — |
| **A+C — Orientar redirecionamento para MTE** | I | **R/A** | — | C *(regra de canal)* | I *(recebe o cidadão)* |
| **B — Solicitar e validar credenciais (autenticação)** | R *(digita credenciais)* | **R** | — | **A** *(valida na base · aplica antifraude)* | — |
| **B — Verbalizar status, data e valor (consulta)** | I | R *(verbaliza via TTS)* | R *(complementa se acionado)* | **A** *(recupera dados via SISGR)* | **C** *(origem dos dados — SISGR/habilitação)* |
| **B — Transferir para atendente e orientar (escalonamento)** | I | R *(transfere)* | **R/A** *(atende · orienta · encaminha)* | C *(limite de alçada)* | I *(recebe casos sem alçada Caixa)* |
| **D — Acolher narrativa e gerar protocolo (registro)** | R *(narra ocorrência)* | R *(acolhe)* | **R/A** *(registra · gera protocolo)* | R *(gestão institucional de reclamações)* | I |
| **D — Orientar canais e rotear manifestação (encaminhamento)** | I | — | R *(orienta)* | **A** *(roteia internamente)* | I *(pode receber reclamo)* |

#### Síntese das responsabilidades por ator

**Cidadão**
Inicia e sustenta toda a jornada — seleciona intenção, fornece credenciais, narra ocorrência. Não tem visibilidade sobre backstage nem sobre a integração Caixa↔MTE. Quando o canal falha, o ônus de encontrar o canal correto recai sobre ele.

**URA Caixa Cidadão**
Ator dominante nas etapas universais e único responsável pelo frontstage dos Ramos A+C e da autenticação no Ramo B. Executa sem discernimento: não distingue contextos individuais além do que o sistema de backend entrega. Não tem autoridade para resolver demandas de solicitação/renovação — redireciona por design.

**Atendente Humano Caixa**
Entra apenas a partir do Ramo B (consulta) e no Ramo D (reclamação). É o único ator com capacidade de julgamento situacional no canal, mas opera com limite de alçada quando a causa-raiz é de responsabilidade do MTE (FP9). Responsável pela geração do protocolo de reclamação no Ramo D.

**Backstage Caixa**
Autoridade técnica sobre autenticação, consulta e gestão de reclamações. Depende dos dados do MTE para executar a consulta (SISGR), criando uma dependência de terceiro invisível ao cidadão. Responsável pela lógica antifraude que pode bloquear permanentemente o acesso remoto (★FP3).

**MTE (ator externo)**
Fonte de dados para todas as consultas do Ramo B e destino obrigatório para solicitação e renovação. Não tem presença direta no canal Caixa — atua como consultado passivo (fornece dados via SISGR) e como receptor dos cidadãos redirecionados. A integração Caixa↔MTE é o ponto cego de maior risco sistêmico do blueprint.
