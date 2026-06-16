# Service Blueprint AS-IS
## Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal (0800 726 0207)

---

## Camadas (swim lanes) presentes no blueprint

Este blueprint segue a metodologia Shostack com **5 camadas horizontais** distinguíveis:
1. **Evidências Físicas** — artefatos, documentos e sinais perceptíveis ao cidadão em cada etapa
2. **Ações do Cidadão** — comportamentos e decisões do usuário ao longo da jornada (perspectiva do cidadão)
3. **Frontstage** — atores e interações visíveis ao cidadão (URA Caixa Cidadão e Atendente humano)
4. **Backstage** — processos internos fora da visibilidade do cidadão (Caixa e lane externa MTE)
5. **Processos de Suporte** — infraestrutura técnica e operacional que sustenta cada etapa

As três linhas divisórias — Linha de Interação (entre Ações do Cidadão e Frontstage), Linha de Visibilidade (entre Frontstage e Backstage) e Linha de Interação Interna (entre Backstage e Processos de Suporte) — estão marcadas como linhas separadoras na tabela principal.

---

## Legenda

| Símbolo | Significado |
|---|---|
| ⚠N | Fail point N (ver tabela ao final) |
| ★ | Fail point crítico — severidade máxima |
| ⬡ | Nó de saída — cidadão deixa o escopo da URA Caixa |
| ~~texto~~ | Ausência crítica — artefato que deveria existir e não existe |
| *itálico* | Inferência — não confirmada por fonte primária no v3 |
| ? | Ponto em aberto — requer validação empírica |

---

## Blueprint

**Espinha dorsal da Jornada B (caminho mais completo — 5 etapas sequenciais na ótica do cidadão):**
Etapa 1 — Conexão → Etapa 2 — Identificação da intenção → Etapa 3 — Autenticação → Etapa 4 — Consulta → Etapa 5 — Escalonamento

*Os Ramos A+C e D compartilham as Etapas 1 e 2 universais; seus desdobramentos pós-bifurcação estão representados nas colunas correspondentes.*

| CAMADA | **ETAPA 1**<br>Conexão ao canal | **ETAPA 2**<br>Identificação da intenção | **↳ ETAPA 3 · RAMO A+C**<br>Redirecionamento externo ¹ | **↳ ETAPA 3 · RAMO B**<br>Autenticação | **↳ ETAPA 4 · RAMO B**<br>Consulta | **↳ ETAPA 5 · RAMO B**<br>Escalonamento | **↳ ETAPA 3-4 · RAMO D**<br>Acolhimento + Registro ² | **↳ ETAPA 5 · RAMO D**<br>Encaminhamento |
|---|---|---|---|---|---|---|---|---|
| **EVIDÊNCIAS FÍSICAS** | Locução/menu URA | Tempo de espera em fila | ~~Protocolo ou comprovante de redirecionamento~~ ⚠1 | Senha Cidadão (6 dígitos DTMF) · Mensagem de bloqueio por tentativas ★ | Status Caixa Tem/Benefícios Sociais Caixa · Status CTPS Digital · Mensagens genéricas de erro ⚠7 · Calendário de pagamento · ~~Aviso de prazo de 67 dias~~ ⚠6 | ~~Confirmação de posição em fila~~ · ~~Callback automático em caso de desconexão~~ ⚠2 | Protocolo de reclamação | ~~Atualização proativa de status da reclamação~~ |
| **AÇÕES DO CIDADÃO** | Disca 0800 726 0207 · Aguarda atendimento da URA | Ouve menu · Seleciona intenção | Ouve orientação · Decide próximo passo: app Carteira de Trabalho Digital / 158 / presencial ⚠1 ⚠10 | Digita CPF/NIS + Senha Cidadão via teclado DTMF ★⚠3 ⚠4 | Ouve ou recebe informação sobre status, data prevista de crédito e valor da parcela ⚠5 ⚠6 ⚠7 ⚠11 | Aguarda transferência · Narra situação ao atendente · Decide próximo passo: aceitar encaminhamento para canal externo OU encerrar ⚠2 ⚠9 | Narra reclamação · Recebe número de protocolo | Decide como acompanhar: Reclame Aqui / Ouvidoria MTE / aguardar retorno ⚠9 |
| **— LINHA DE INTERAÇÃO —** | | | | | | | | |
| **FRONTSTAGE**<br>*URA Caixa Cidadão* | Atende chamada · Reproduz locução inicial | Apresenta menu de opções · Classifica intenção selecionada | Informa que solicitação/renovação é fora do escopo resolutivo Caixa · Orienta canais MTE ⚠1 ⚠10 | Solicita CPF/NIS e Senha Cidadão · Processa DTMF · Retorna: (i) autenticado ✓ / (ii) sem senha cadastrada → orienta cadastro / (iii) senha bloqueada → ★ destino indeterminado ? ⚠3 ⚠4 | Verbaliza situação do benefício, data prevista de crédito e valor da parcela ⚠5 ⚠7 ⚠11 | Informa posição em fila · Transfere para atendente humano ⚠2 | Acolhe narrativa · Registra manifestação · Gera e comunica protocolo | Orienta canais de acompanhamento da reclamação |
| **FRONTSTAGE**<br>*Atendente humano Caixa* | — | — | — | — | Complementa ou aprofunda informação da URA quando acionado | Recebe caso · Informa status disponível · Orienta canais externos quando sem alçada ⚠9 | — | — |
| **— LINHA DE VISIBILIDADE —** | | | | | | | | |
| **BACKSTAGE**<br>*Núcleo operacional Caixa* | Roteia chamada · Inicializa sessão | Classifica demanda · Prepara fluxo subsequente | Aplica regra de canal: intenção classificada como fora do escopo resolutivo → aciona ramo de encaminhamento. Sem log individual de demanda desviada presumido | Valida Senha Cidadão em base Caixa · Verifica estado da credencial · Aplica lógica antifraude por tentativas ★⚠3 | Recupera dados via SISGR (dados de origem MTE) · Sujeito a divergências por múltiplas visões, *defasagem de sincronização* ou rejeição/retorno de crédito ⚠5 ⚠6 ⚠8 ⚠11 | Passa caso para camada humana · *Abre chamado interno (se aplicável)* · Identifica limite de alçada quando solução depende do MTE | Entrada em camada institucional de gestão de reclamações · *Possível distinção prática entre temas Caixa e temas MTE* | *Roteamento interno da manifestação* |
| **BACKSTAGE**<br>*Lane externa — MTE* | — | — | ⬡ Destino dos cidadãos redirecionados (triagem/habilitação) — fora do escopo deste blueprint ⁶ | — | Origem dos dados consultados (sistema de habilitação MTE) · *Integração com possível defasagem — mecanismo não confirmado* ? ⚠5 | ⬡ Destino de casos sem alçada Caixa ⚠9 | — | ⬡ Ouvidoria MTE como destino externo |
| **— LINHA DE INTERAÇÃO INTERNA —** | | | | | | | | |
| **PROCESSOS DE SUPORTE** | Infraestrutura URA/0800 · Telefonia · Regras de desenho do serviço | Lógica de menu · Base institucional de canais de encaminhamento | Base atualizada de canais de destino (app Carteira de Trabalho Digital, Portal Emprega Brasil, central 158, postos SINE/SRTE) · Lógica de orientação por intenção | Ecossistema Cartão Cidadão/Senha Cidadão · Sistema antifraude de bloqueio por tentativas · Infraestrutura DTMF · *Rede lotérica para cadastro e regularização de senha* ⁴ ⚠4 | SISGR · Sistema de habilitação MTE · *Integração Caixa↔MTE (mecanismo indeterminado — batch vs. tempo real)* ? · Apps do ecossistema (Caixa Tem, Benefícios Sociais Caixa, Caixa Trabalhador) | Atendimento humano Caixa · Central 158 · Agência física · *Reclame Aqui* · Ouvidoria MTE · Procon · Defensoria · *(sem integração plena confirmada entre eles)* | 0800 · Infraestrutura de protocolo · Reclame Aqui (canal oficial Caixa) | Reclame Aqui · Ouvidoria MTE · Procon · Defensoria |

---

## Notas estruturais

| # | Nota |
|---|---|
| ¹ | **Ramo A+C** representa fluxo único de redirecionamento com variação de gatilho: Jornada A = 1ª solicitação / Jornada C = renovação (2ª, 3ª+ solicitação). O fluxo no canal Caixa é idêntico em ambas. |
| ² | **Autenticação** não é etapa estrutural na Jornada D — o v3 não sustenta isso com a mesma robustez da Jornada B. No máximo, nota lateral de eventual identificação do reclamante em D, não representada como etapa. |
| ³ | **Comprovante de saque/extrato** aparece como evidência física terminal apenas quando há crédito efetivo — não integra nenhuma etapa das jornadas mapeadas; é pós-blueprint. *Sem marcador em célula da tabela — refere-se a item intencionalmente fora do escopo principal.* |
| ⁴ | **Apps Caixa, lotérica e canal PcD** (0800 726 2492) não integram lanes principais — tratados como suporte, handoff pontual ou canal complementar. |
| ⁵ | **FAT/CODEFAT, eSocial, CAGED e RAIS** não são modelados como atores — decisão de escopo para manter o foco no atendimento pela URA e não migrar para a governança completa do benefício. *Sem marcador em célula da tabela — refere-se a atores intencionalmente excluídos do blueprint.* |
| ⁶ | **Nós de saída** (⬡): 158/MTE, Agência física, Posto SINE/SRTE, Ouvidoria MTE — o cidadão sai do escopo da URA Caixa nestes pontos. A jornada pode ter continuidade nesses canais, mas está fora do perímetro deste blueprint. |

---

## Complexidade das jornadas por variação de entrada

### Jornada A — 1ª solicitação (Ramo A+C)

| Fase | Descrição | Complexidade operacional |
|---|---|---|
| **Dentro do canal Caixa** | Etapa 3: URA redireciona verbalmente — sem protocolo entregue ⚠1 | Baixa: 1 etapa, 0 resolução |
| **Pós-redirecionamento (fora do escopo Caixa)** | Cidadão tenta app Carteira de Trabalho Digital ou Portal Emprega Brasil | Exige smartphone + conta Gov.br validada (barreira de inclusão digital) |
| **Cenário de falha pós-redirecionamento** | Cidadão sem smartphone/dados/Gov.br validado não consegue completar no digital | Loop: nova ligação para 0800 726 0207 sem informação acumulada do contato anterior (v3 §1.1) |
| **Carência exigida (normativo)** | Mínimo 12 meses nos últimos 18 meses imediatamente anteriores à dispensa | Cidadão que não atende não tem direito — a URA não valida carência antes de redirecionar |
| **Parcelas (se elegível)** | 4 parcelas (12–23 meses) ou 5 parcelas (≥24 meses) | A faixa de "3 parcelas" NÃO existe para a 1ª solicitação (v3 §6.2) |

### Jornada C — Renovação / 2ª ou 3ª+ solicitação (Ramo A+C)

| Fase | Descrição | Diferença em relação à Jornada A |
|---|---|---|
| **Dentro do canal Caixa** | Idêntica à Jornada A — mesma etapa de redirecionamento ⚠1 | Nenhuma: o canal Caixa não distingue 1ª solicitação de renovação |
| **Carência exigida (normativo)** | 2ª solicitação: 9 meses nos últimos 12 meses / 3ª+: cada um dos 6 meses anteriores | Regra mais permissiva que na 1ª solicitação |
| **Parcelas (se elegível)** | 2ª sol.: 3–5 parcelas (9–11 m. / 12–23 m. / ≥24 m.) · 3ª+ sol.: 3–5 parcelas (6–11 m. / 12–23 m. / ≥24 m.) | A faixa de "3 parcelas" existe a partir da 2ª solicitação |
| **Risco específico** | Confusão entre faixas de parcelas por número de solicitação — atendente pode aplicar tabela errada ⚠11 | Mais grave que na 1ª solicitação: cidadão tem histórico, gera expectativa de número diferente |

### Jornada D — Reclamação formal (Ramo D)

| Etapa | Descrição | Limitações operacionais |
|---|---|---|
| **Etapa 3-D — Acolhimento** | URA ou atendente acolhe narrativa do cidadão | Sem triagem prévia de causa-raiz: Caixa ou MTE? |
| **Etapa 4-D — Registro** | Manifestação registrada · protocolo gerado | Sem prazo claro de resolução · sem atualização proativa confirmada |
| **Etapa 5-D — Encaminhamento** | Orientação sobre canais de acompanhamento · roteamento interno | Empurra-empurra Caixa↔MTE ⚠9: cidadão pode ser redirecionado ao MTE para problema de competência Caixa |
| **Desfecho típico** | Resposta institucional reitera "gestão é do MTE, Caixa só paga" | Do ponto de vista do cidadão: repasse de responsabilidade sem resolução (v3 §1.4) |

---

## Fail points posicionados

| # | Fail point | Etapa | Ramo | Camada | Severidade |
|---|---|---|---|---|---|
| ⚠1 | Canal errado para iniciar — cidadão que liga para solicitar/renovar é redirecionado sem resolução no canal Caixa | Redirecionamento | A+C | Frontstage + Evidências Físicas | Alta |
| ⚠2 | Queda de ligação antes do atendente humano, sem callback automático relatado | Escalonamento | B | Frontstage + Evidências Físicas | Alta |
| ★3 | **Bloqueio de Senha Cidadão por tentativas DTMF incorretas — caminho de desbloqueio indeterminado (remoto vs. presencial). Risco de severidade mais subestimado do blueprint** | Autenticação | B | Ações do Cidadão + Frontstage + Backstage | **Crítica** |
| ⚠4 | Dependência de etapa presencial obrigatória (lotérica) para cadastro e regularização de Senha Cidadão | Autenticação | B | Frontstage + Processos de Suporte | Alta |
| ⚠5 | Divergência de status entre sistemas Caixa e MTE — múltiplas visões dos mesmos dados, *possível defasagem de sincronização não confirmada* | Consulta | B | Frontstage + Backstage | Alta |
| ⚠6 | Retorno/rejeição de crédito com janela de até 67 dias até devolução ao FAT — invisível ao cidadão como status distinto; ausência do aviso como evidência física crítica | Consulta | B | Backstage + Evidências Físicas | Alta |
| ⚠7 | Mensagens genéricas de erro — não acionáveis, sem causa raiz nem direcionamento específico | Consulta | B | Frontstage + Evidências Físicas | Média |
| ⚠8 | Falhas sistêmicas em lote (ex.: incidente jun/2025) com comunicação defasada — provavelmente amplifica o ⚠6 em volume anormal | Consulta | B | Backstage | Alta |
| ⚠9 | Empurra-empurra institucional Caixa↔MTE — repasse de responsabilidade sem resolução do ponto de vista do cidadão | Escalonamento | B+D | Frontstage + Backstage | Alta |
| ⚠10 | Prazo de requerimento perdido — cidadão que liga fora da janela de 7 a 120 dias após demissão não pode ser habilitado; reversão apenas por erro comprovado do sistema ou decisão judicial (v3 §1.3 e §6.4) | Redirecionamento | A+C | Frontstage | Alta |
| ⚠11 | Confusão entre faixas de parcelas por número de solicitação — aplicação da tabela genérica "6–11 meses = 3 parcelas" a cidadão na 1ª solicitação gera expectativa de direito inexistente, pois esse perfil não atende à carência mínima de 12 meses (v3 §6.2 e §7 item 15) | Consulta | B | Frontstage + Backstage | Alta |

---

## Diagnóstico Sistêmico

A análise dos 11 fail points revela quatro padrões de causa transversais ao serviço:

| Padrão diagnóstico | Fail points | Causa raiz identificada | Impacto no cidadão |
|---|---|---|---|
| **Fragmentação de canal e competência** | ⚠1 · ⚠9 · ⚠10 | O canal Caixa não tem alçada resolutiva para solicitação/renovação; MTE e Caixa transferem responsabilidade sem resolução | Cidadão sai sem protocolo, reinicia jornada do zero, pode perder prazo sem aviso |
| **Opacidade sistêmica das integrações** | ⚠5 · ⚠6 · ⚠8 | Integração Caixa↔MTE com mecanismo indeterminado (batch vs. tempo real); retorno de crédito invisível ao cidadão como status distinto | Divergência de status entre canais; perda silenciosa do benefício na janela de 67 dias |
| **Dependência de presença física em serviço remoto** | ★⚠3 · ⚠4 | Falhas de autenticação digital forçam lotérica/agência sem garantia de resolução remota — contradição estrutural do canal telefônico | Canal remoto se torna inacessível exatamente quando o cidadão mais depende dele |
| **Informação incorreta ou ausente nos pontos críticos** | ⚠7 · ⚠10 · ⚠11 | Mensagens genéricas sem causa-raiz; ausência de comunicação proativa do prazo de 67 dias; aplicação de tabela errada de parcelas sem distinção por número de solicitação | Expectativas de direito falsas; perda de benefício por desinformação; reclamações formais sem base de resolução |

---

## Pontos em aberto prioritários para validação empírica

| Prioridade | Item em aberto | Impacto no blueprint | Método sugerido (v3, §8.2) |
|---|---|---|---|
| **1 — Crítico** | Caminho de desbloqueio da Senha Cidadão (★FP3): remoto ou obrigatoriamente presencial? | Define o desfecho do ramo (iii) da autenticação — hoje marcado como indeterminado; não pode ser assumido | Ligação de teste com erros deliberados de DTMF; ou consulta à documentação interna da Caixa distinguindo "recadastro" de "desbloqueio por tentativas" |
| **2 — Alto** | Árvore real de menus da URA: estrutura exata, reconhecimento de voz vs. DTMF, ponto exato de coleta de credenciais | Detalha as etapas 1 e 2 e o início do ramo de autenticação | Shadowing / ligação de teste real |
| **3 — Médio** | Mecanismo de sincronização Caixa↔MTE: batch com defasagem vs. tempo real via API | Confirma ou refuta a causa estrutural do ⚠FP5 e a latência do ⚠FP8 | Acesso institucional direto ou pedido via LAI ao MTE/Caixa |

---

## Rastreabilidade de decisões

Esta seção registra as decisões tomadas pelo usuário durante a construção facilitada do blueprint (metodologia Shostack), para fins de auditoria e revisão futura.

| Decisão | Conteúdo |
|---|---|
| Escopo | Blueprint único com quatro variações de entrada (A, B, C, D), circunscrito às interações com a Caixa (URA + atendente humano) e aos handoffs para o ecossistema externo |
| Espinha dorsal | Duas etapas universais (conexão + identificação da intenção) seguidas de três ramos distintos: A+C (redirecionamento), B (autenticação → consulta → escalonamento), D (acolhimento + registro → encaminhamento) |
| Autenticação | Não é etapa universal — central em B, ausente como etapa estrutural em D (nota lateral de eventual identificação) |
| Ramo A+C | Fluxo único com nota de variação de gatilho (1ª solicitação vs. renovação) |
| Atores externos | 158/MTE, agência física, posto SINE/SRTE representados como nós de saída (⬡), não como lanes |
| Backstage MTE | Lane externa única (triagem/habilitação); FAT/CODEFAT, eSocial, CAGED e RAIS excluídos como atores |
| Lanes secundárias | Apps Caixa, lotérica e canal PcD fora das lanes principais — suporte ou handoff pontual |
| Jornada D | Mantida curta: acolhimento, protocolo, encaminhamento — sem workflow interno detalhado |
| Fail point crítico | ★FP3 (bloqueio de Senha Cidadão) recebe marcação diferenciada como o de maior risco de severidade subestimada |
| Ausência crítica | ~~Aviso de 67 dias~~ representado como evidência física ausente na etapa de consulta |
| Base factual | Pesquisa AS-IS v3 — `B_relatorio_assistente_v3.md` |
| Metodologia de construção | Sessão grill facilitada (Shostack) — `C_grill_transcript.md` — todas as decisões acima derivam das respostas do usuário durante a sessão |
| Ausência crítica Ramo A+C | Cidadão sai do canal Caixa sem protocolo ou comprovante de redirecionamento — marcado como ~~ausência~~ na camada de Evidências Físicas (⚠1) |
| ⚠10 — Prazo de requerimento | Decidido na sessão grill (complemento pós-refinamento final) — etapa: Redirecionamento (A+C), Frontstage URA; derivado de v3 §1.3 e §6.4. Alinha com os demais fail points estruturais do Ramo A+C |
| ⚠11 — Confusão de parcelas por nº de solicitação | Decidido na sessão grill (complemento pós-refinamento final) — etapa: Consulta (B), Frontstage URA + Backstage Caixa; derivado de v3 §6.2 e §7 item 15. Complementa ⚠FP14 (v3) sobre confusão entre modalidades |

---

## Tabela RACI — Responsabilidades e interações entre atores

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

### Síntese das responsabilidades por ator

**Cidadão** — Inicia e sustenta toda a jornada. Não tem visibilidade sobre backstage nem sobre a integração Caixa↔MTE. Quando o canal falha, o ônus de encontrar o canal correto recai sobre ele.

**URA Caixa Cidadão** — Ator dominante nas etapas universais e único responsável pelo frontstage dos Ramos A+C e da autenticação no Ramo B. Executa sem discernimento contextual individual além do que o backend entrega. Não tem autoridade para resolver demandas de solicitação/renovação — redireciona por design.

**Atendente Humano Caixa** — Entra apenas a partir do Ramo B (consulta) e no Ramo D (reclamação). Único ator com capacidade de julgamento situacional no canal, mas opera com limite de alçada quando a causa-raiz é de responsabilidade do MTE (⚠9).

**Backstage Caixa** — Autoridade técnica sobre autenticação, consulta e gestão de reclamações. Depende dos dados do MTE para executar a consulta (SISGR), criando uma dependência de terceiro invisível ao cidadão. Responsável pela lógica antifraude que pode bloquear permanentemente o acesso remoto (★FP3).

**MTE (ator externo)** — Fonte de dados para todas as consultas do Ramo B e destino obrigatório para solicitação e renovação. Não tem presença direta no canal Caixa — atua como consultado passivo (fornece dados via SISGR) e como receptor dos cidadãos redirecionados. A integração Caixa↔MTE é o ponto cego de maior risco sistêmico do blueprint.

*Ver também: `D_diagrama_asis.md` — diagrama Mermaid com representação visual desta estrutura de responsabilidades.*
