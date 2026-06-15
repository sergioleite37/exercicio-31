# Service Blueprint AS-IS
## Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal (0800 726 0207)

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

| CAMADA | **ETAPA 1**<br>Conexão ao canal | **ETAPA 2**<br>Identificação da intenção | **↳ ETAPA 3 · RAMO A+C**<br>Redirecionamento externo ¹ | **↳ ETAPA 3 · RAMO B**<br>Autenticação | **↳ ETAPA 4 · RAMO B**<br>Consulta | **↳ ETAPA 5 · RAMO B**<br>Escalonamento | **↳ ETAPA 3-4 · RAMO D**<br>Acolhimento + Registro | **↳ ETAPA 5 · RAMO D**<br>Encaminhamento |
|---|---|---|---|---|---|---|---|---|
| **EVIDÊNCIAS FÍSICAS** | Locução/menu URA | Tempo de espera em fila | ~~Protocolo ou comprovante de redirecionamento~~ ⚠1 | Senha Cidadão (6 dígitos DTMF) · Mensagem de bloqueio por tentativas ★ | Status Caixa Tem/Benefícios Sociais Caixa · Status CTPS Digital · Mensagens genéricas de erro · Calendário de pagamento · ~~Aviso de prazo de 67 dias~~ ⚠6 | — | Protocolo de reclamação | — |
| **— LINHA DE INTERAÇÃO —** | | | | | | | | |
| **AÇÕES DO CIDADÃO / USUÁRIO** | Disca 0800 726 0207 · Aguarda atendimento da URA | Ouve menu · Seleciona intenção | Ouve orientação · Decide próximo passo: app Carteira de Trabalho Digital / 158 / presencial | Digita CPF/NIS + Senha Cidadão via teclado DTMF | Ouve ou recebe informação sobre status, data prevista de crédito e valor da parcela | Aguarda transferência · Narra situação ao atendente · Recebe orientação ou é redirecionado para outro canal/órgão | Narra reclamação · Recebe número de protocolo | Aguarda retorno institucional ou é orientado sobre próximos passos |
| **— LINHA DE INTERAÇÃO —** | | | | | | | | |
| **FRONTSTAGE**<br>*(linha de frente visível — sistema automatizado)*<br>*URA Caixa Cidadão* | Atende chamada · Reproduz locução inicial | Apresenta menu de opções · Classifica intenção selecionada | Informa que solicitação/renovação é fora do escopo resolutivo Caixa · Orienta canais MTE ⚠1 | Solicita CPF/NIS e Senha Cidadão · Processa DTMF · Retorna: (i) autenticado ✓ / (ii) sem senha cadastrada → orienta cadastro / (iii) senha bloqueada → ★ destino indeterminado ? ⚠3 ⚠4 | Verbaliza situação do benefício, data prevista de crédito e valor da parcela ⚠5 ⚠7 | Informa posição em fila · Transfere para atendente humano ⚠2 | Acolhe narrativa · Registra manifestação · Gera e comunica protocolo ² | Orienta canais de acompanhamento da reclamação |
| **FRONTSTAGE**<br>*(linha de frente visível — ator humano)*<br>*Atendente humano Caixa* | — | — | — | — | Complementa ou aprofunda informação da URA quando acionado | Recebe caso · Informa status disponível · Orienta canais externos quando sem alçada ⚠9 | — | — |
| **— LINHA DE VISIBILIDADE —** | | | | | | | | |
| **BACKSTAGE**<br>*Núcleo operacional Caixa* | Roteia chamada · Inicializa sessão | Classifica demanda · Prepara fluxo subsequente | Aplica regra de canal: intenção classificada como fora do escopo resolutivo → aciona ramo de encaminhamento. Sem log individual de demanda desviada presumido | Valida Senha Cidadão em base Caixa · Verifica estado da credencial · Aplica lógica antifraude por tentativas | Recupera dados via SISGR (dados de origem MTE) · Sujeito a divergências por múltiplas visões, *defasagem de sincronização* ou rejeição/retorno de crédito ⚠5 ⚠6 ⚠8 | Passa caso para camada humana · *Abre chamado interno (se aplicável)* · Identifica limite de alçada quando solução depende do MTE | Entrada em camada institucional de gestão de reclamações · *Possível distinção prática entre temas Caixa e temas MTE* | *Roteamento interno da manifestação* |
| **BACKSTAGE**<br>*Lane externa — MTE* | — | — | ⬡ Destino dos cidadãos redirecionados (triagem/habilitação) — fora do escopo deste blueprint | — | Origem dos dados consultados (sistema de habilitação MTE) · *Integração com possível defasagem — mecanismo não confirmado* ? ⚠5 | ⬡ Destino de casos sem alçada Caixa ⚠9 | — | ⬡ Ouvidoria MTE como destino externo |
| **— LINHA DE INTERAÇÃO INTERNA —** | | | | | | | | |
| **PROCESSOS DE SUPORTE** | Infraestrutura URA/0800 · Telefonia · Regras de desenho do serviço | Lógica de menu · Base institucional de canais de encaminhamento | Base atualizada de canais de destino (app Carteira de Trabalho Digital, Portal Emprega Brasil, central 158, postos SINE/SRTE) · Lógica de orientação por intenção | Ecossistema Cartão Cidadão/Senha Cidadão · Sistema antifraude de bloqueio por tentativas · Infraestrutura DTMF · *Rede lotérica para cadastro e regularização de senha* | SISGR · Sistema de habilitação MTE · *Integração Caixa↔MTE (mecanismo indeterminado — batch vs. tempo real)* ? · Apps do ecossistema (Caixa Tem, Benefícios Sociais Caixa, Caixa Trabalhador) | Atendimento humano Caixa · Central 158 · Agência física · *Reclame Aqui* · Ouvidoria MTE · Procon · Defensoria · *(sem integração plena confirmada entre eles)* | 0800 · Infraestrutura de protocolo · Reclame Aqui (canal oficial Caixa) | Reclame Aqui · Ouvidoria MTE · Procon · Defensoria |

---

## Notas estruturais

| # | Nota |
|---|---|
| ¹ | **Ramo A+C** representa fluxo único de redirecionamento com variação de gatilho: Jornada A = 1ª solicitação / Jornada C = renovação (2ª, 3ª+ solicitação). O fluxo no canal Caixa é idêntico em ambas. |
| ² | **Autenticação** não é etapa estrutural na Jornada D — o v3 não sustenta isso com a mesma robustez da Jornada B. No máximo, nota lateral de eventual identificação do reclamante em D, não representada como etapa. |
| ³ | **Comprovante de saque/extrato** aparece como evidência física terminal apenas quando há crédito efetivo — não integra nenhuma etapa das jornadas mapeadas; é pós-blueprint. |
| ⁴ | **Apps Caixa, lotérica e canal PcD** (0800 726 2492) não integram lanes principais — tratados como suporte, handoff pontual ou canal complementar. |
| ⁵ | **FAT/CODEFAT, eSocial, CAGED e RAIS** não são modelados como atores — decisão de escopo para manter o foco no atendimento pela URA e não migrar para a governança completa do benefício. |
| ⁶ | **Nós de saída** (⬡): 158/MTE, Agência física, Posto SINE/SRTE, Ouvidoria MTE — o cidadão sai do escopo da URA Caixa nestes pontos. A jornada pode ter continuidade nesses canais, mas está fora do perímetro deste blueprint. |

---

## Fail points posicionados

| # | Fail point | Etapa | Ramo | Severidade |
|---|---|---|---|---|
| ⚠1 | Canal errado para iniciar — cidadão que liga para solicitar/renovar é redirecionado sem resolução no canal Caixa | Redirecionamento | A+C | Alta |
| ⚠2 | Queda de ligação antes do atendente humano, sem callback automático relatado | Escalonamento | B | Alta |
| ★3 | **Bloqueio de Senha Cidadão por tentativas DTMF incorretas — caminho de desbloqueio indeterminado (remoto vs. presencial). Risco de severidade mais subestimado do blueprint** | Autenticação | B | **Crítica** |
| ⚠4 | Dependência de etapa presencial obrigatória (lotérica) para cadastro e regularização de Senha Cidadão | Autenticação | B | Alta |
| ⚠5 | Divergência de status entre sistemas Caixa e MTE — múltiplas visões dos mesmos dados, *possível defasagem de sincronização não confirmada* | Consulta | B | Alta |
| ⚠6 | Retorno/rejeição de crédito com janela de até 67 dias até devolução ao FAT — invisível ao cidadão como status distinto; ausência do aviso como evidência física crítica | Consulta | B | Alta |
| ⚠7 | Mensagens genéricas de erro — não acionáveis, sem causa raiz nem direcionamento específico | Consulta | B | Média |
| ⚠8 | Falhas sistêmicas em lote (ex.: incidente jun/2025) com comunicação defasada — provavelmente amplifica o ⚠6 em volume anormal | Backstage — Consulta | B | Alta |
| ⚠9 | Empurra-empurra institucional Caixa↔MTE — repasse de responsabilidade sem resolução do ponto de vista do cidadão | Escalonamento | B+D | Alta |

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
