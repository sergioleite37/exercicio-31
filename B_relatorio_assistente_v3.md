# Pesquisa AS-IS v3 (Versão Final) — Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal

## Nota de versão

Esta v3 é a versão consolidada e final da pesquisa, incorporando: (i) a estrutura original (v1); (ii) as correções da v2 em resposta à Auditoria v1; e (iii) os ajustes desta v3 em resposta à **Auditoria v2**. A v3 não está mais organizada como "resposta a uma auditoria" — ela é a **pesquisa em si**, organizada nas 8 dimensões que sustentam o Service Blueprint AS-IS. Onde um ajuste decorre de um achado específico da Auditoria v2, isso é sinalizado inline com a marca **[Auditoria v2 — item N]**.

### Mapa de rastreabilidade: Auditoria v2 → v3

| Item Auditoria v2 | Classificação da auditoria | Ação na v3 | Onde |
|---|---|---|---|
| 1 — Regras de carência e parcelas (trabalhador formal) | Falha v1 não resolvida + Nova falha factual | **Reescrita integral** da Seção 6.2 — tabela unificada carência × parcelas, parametrizada por número de solicitação (1ª/2ª/3ª+) | Seção 6.2; reflete em Seção 1 (Jornada C) e Seção 7 (novo fail point #15) |
| 2 — Conciliação/devolução de crédito (67 dias) | Falha v1 resolvida | **Mantido** — estrutura da v2 preservada sem alteração | Seções 4 (item 4-bis) e 7 (fail point #13) |
| 3 — Bloqueio de Senha Cidadão (DTMF) e recuperação | Falha v1 resolvida, com Ponto Aberto crítico | **Formalização**: a ruptura é marcada explicitamente na Jornada (2-bis) e no Fail Point #12 como "ruptura sem caminho de resolução mapeado — requer investigação empírica", conforme recomendado | Seções 1, 7 e 8 |
| 4 — LGPD e limites do TTS | Falha v1 parcialmente resolvida + Ponto Aberto | **Mantido como pendente**, com linguagem fortalecida: explicitamente classificado como fora do alcance de fontes abertas (não apenas "não encontrado", mas "não localizável por pesquisa em fontes primárias públicas") | Seções 6.8 e 8 |
| 5 — Convênio/SLA MTE-Caixa | Ponto Aberto | **Refinamento**: incorporada a sugestão da auditoria de que o instrumento provavelmente é um **Termo de Execução Descentralizada (TED)** ou instrumento correlato — mantido como pendente, mas com alvo de busca mais específico para LAI | Seções 5 e 8 |
| 6 — Inferência sobre limitações tecnológicas da URA | Falha v1 resolvida — nenhuma ação requerida | **Mantido sem alteração** | Seção 1 (Jornada C) e Seção 7 |

---

## 1. Jornada do Cidadão

A jornada continua organizada em quatro variações (A–D), pois o canal 0800 726 0207 é compartilhado entre múltiplas intenções do cidadão.

### 1.1 Jornada A — Solicitar o benefício pela primeira vez (qualquer modalidade)

1. **Gatilho:** demissão sem justa causa (ou outra hipótese elegível); recebimento (ou não) do Requerimento do Seguro-Desemprego do empregador.
2. **Primeiro contato:** ligação para 0800 726 0207 (Caixa Cidadão), por ser o número mais lembrado/divulgado para benefícios sociais.
3. **Ponto de decisão 1 — Desvio de canal:** a URA identifica que "solicitação" não é feita pela Caixa, e orienta o uso do app Carteira de Trabalho Digital, Portal Gov.br/Emprega Brasil, ou comparecimento a posto SINE/SRTE (agendamento via 158).
4. **Bifurcação:**
   - **Caminho 1 (digital):** cidadão é direcionado ao app Carteira de Trabalho Digital — jornada telefônica com a Caixa termina sem resolução, redirecionando para outro órgão/login (conta Gov.br).
   - **Caminho 2 (presencial):** cidadão liga para 158 (Alô Trabalho/MTE) para agendar atendimento em SRTE/SINE — segundo canal telefônico, com horários e filas próprios (seg-sáb, 7h–19h).
5. **Ponto de ruptura:** cidadão sem smartphone/dados/conta Gov.br validada pode entrar em **loop** entre Caixa → orientação digital → incapacidade de executar → nova ligação à Caixa.
6. **Conclusão "de sucesso":** requerimento formalizado em outro canal → entra na Jornada B.

> **Nota normativa (reforçada na v3):** o sucesso desta jornada depende criticamente de o cidadão atender à **carência mínima de elegibilidade para a 1ª solicitação (12 meses nos últimos 18)** — ver tabela unificada na Seção 6.2. Se o cidadão não atende a esse mínimo, **nenhum canal** (URA, 158, app, presencial) pode "aprovar" o pedido — a ruptura, nesse caso, é normativa, não operacional.

### 1.2 Jornada B — Consultar status/parcela já solicitada

1. **Gatilho:** benefício já requerido; cidadão quer saber se foi habilitado, quantas parcelas, datas, ou por que uma parcela não foi paga.
2. **Primeiro contato:** 0800 726 0207 — atendimento eletrônico 24h/7; atendimento humano seg-sáb (faixas de horário variam entre fontes: 8h–21h/22h em dias úteis, 10h–16h sábado).
3. **Autenticação na URA (hipótese — ver Seção 8):** CPF e/ou NIS/PIS, seguido de Senha Cidadão (6 dígitos numéricos via teclado).
4. **Ponto de decisão 2 — Cidadão não possui senha cadastrada:** cadastro por telefone existe, mas exige confirmação presencial em casa lotérica ~2h depois — o "canal telefônico" não é autossuficiente.
5. **Ponto de decisão 2-bis — Bloqueio de Senha Cidadão por excesso de tentativas incorretas [Auditoria v2 — item 3]:** diferente do item 4 (nunca cadastrou), aqui o cidadão **tinha** senha válida, mas a digitação repetida incorreta no teclado numérico (DTMF) aciona bloqueio antifraude **dentro da própria ligação**. Este é um ponto de ruptura formalmente marcado como **sem caminho de resolução mapeado**: não está confirmado se o desbloqueio é remoto (telefone/internet, mediante validação alternativa) ou exige obrigatoriamente agência/lotérica física. **Esta ambiguidade é tratada como item crítico em aberto (Seção 8, item 12)** — até sua resolução, o blueprint deve representar este ramo como "destino indeterminado", e não assumir nem o caminho remoto nem o presencial.
6. **Consulta bem-sucedida (se autenticado):** sistema informa situação do benefício, data prevista de crédito, valor da parcela — dados de origem MTE, consultados via interface Caixa (SISGR).
7. **Ponto de ruptura — Discrepância entre canais:** status "emitida" (Carteira de Trabalho Digital) vs. "crédito bloqueado" (Caixa Tem/Benefícios Sociais Caixa) vs. "sem pendência" (atendente Caixa) no mesmo dia. Causas possíveis incluem:
   - Defasagem de sincronização Caixa↔MTE (não confirmada — Seção 8);
   - **Retorno/rejeição de crédito em conciliação [Auditoria v1 — Falha 2 / v2 item 4-bis]:** se a causa raiz for um crédito devolvido à Caixa (conta encerrada, dados incorretos, falha de transferência), o cidadão entra em uma **janela de até 67 dias** (Resolução CODEFAT 957/2022) até que o valor seja efetivamente devolvido ao FAT — durante essa janela, o status pode permanecer "indefinido" para o cidadão, indistinguível de "só está demorando".
8. **Ponto de ruptura — Queda de chamada:** ligações interrompidas antes do atendente humano, especialmente em horários de pico, sem callback automático relatado.
9. **Escalonamento:** atendente humano Caixa Cidadão → central 158/MTE → agência física → canais digitais (chat/app) → órgãos externos (Ouvidoria MTE, Procon, Defensoria).

### 1.3 Jornada C — Renovar/solicitar novamente (2ª, 3ª+ solicitação)

1. **Gatilho:** nova demissão após período empregado; cidadão quer requerer novamente.
2. **Diferença-chave — carência e parcelas variam por número de solicitação [reescrito conforme Auditoria v2 — item 1 e item 6]:**
   > As regras de **carência** (elegibilidade) e de **número de parcelas** mudam conforme a solicitação ser a 1ª, 2ª ou 3ª+ — **e são duas tabelas relacionadas, mas distintas**, ambas detalhadas na tabela unificada da Seção 6.2. **Diferentemente do que versões anteriores desta pesquisa sugeriram, não existe uma tabela única "6–11 meses = 3 parcelas" válida para qualquer solicitação** — essa faixa de 3 parcelas só vale a partir da 3ª solicitação (ou, com limiar diferente — 9 a 11 meses —, na 2ª solicitação). Na 1ª solicitação, **não existe a hipótese de 3 parcelas**: o mínimo é 4 (para 12–23 meses) e o máximo é 5 (24+ meses) — consistente com a própria carência da 1ª solicitação já exigir 12 meses mínimos.
   >
   > **Sobre a capacidade da URA de informar isso [mantido da v2 — Auditoria v2 item 6, "nenhuma ação requerida"]:** a limitação da URA em antecipar o resultado de uma *nova* solicitação não decorre de ela ser um "sistema de áudio pré-gravado" (URAs modernas com API+TTS podem verbalizar dados individualizados, como demonstrado na Jornada B). A limitação é **estrutural/temporal**: a avaliação de carência e o cálculo de parcelas de uma nova solicitação só ocorrem **durante o processamento do requerimento em si** (pré-triagem/triagem do MTE), não antes. A URA pode, no máximo, informar as regras gerais (texto fixo) — porque o dado individualizado ainda não existe nesse ponto da jornada, não porque a URA seja incapaz de verbalizar dados dinâmicos.
3. **Caminho:** como na Jornada A, o cidadão é direcionado para app Carteira de Trabalho Digital / Portal Emprega Brasil / posto SINE — a URA da Caixa não processa "renovação".
4. **Ponto de ruptura — Prazo perdido:** se o cidadão perdeu a janela de requerimento (7º–120º dia, com a divergência de 90 vs. 120 dias para trabalhador formal ainda em aberto — Seção 8), o sistema "trava" a solicitação; reversão só por erro comprovado do sistema ou decisão judicial.

### 1.4 Jornada D — Registrar reclamação formal

1. **Gatilho:** parcela não paga, bloqueio indevido, atendimento anterior insatisfatório.
2. **Caminho oficial:** 0800 726 0207 atende reclamações ("registrar a reclamação na opção desejada").
3. **Caminho alternativo observado:** Reclame Aqui (canal oficial assumido pela Caixa), redes sociais, Procon, Ouvidoria do MTE (0800 702 1111) — sugere que o canal telefônico é percebido como registro inicial, não como canal de resolução.
4. **Ponto de ruptura:** respostas institucionais reiteram "gestão é do MTE, Caixa só paga" — do ponto de vista do cidadão, repassa responsabilidade sem necessariamente resolver (ex.: dinheiro não creditado).

---

## 2. Evidências Físicas e Perceptíveis em Cada Etapa

| Evidência | Onde aparece | Qualidade/Clareza observada |
|---|---|---|
| **Requerimento do Seguro-Desemprego (RSD)** | Documento entregue pelo empregador; pré-requisito | Documento "chave"; parcialmente digitalizado via Carteira de Trabalho Digital |
| **Locução/menu da URA (0800 726 0207)** | Primeiro contato | Cobre PIS, Seguro-Desemprego, FGTS, Cartão Social, SIC, loterias no mesmo número — potencial confusão de navegação |
| **Tempo de espera/fila (hold)** | Tentativa de falar com humano | Relatado como longo o suficiente para "cair" — sem TME público |
| **Status "Carteira de Trabalho Digital"** | Consulta digital (MTE) | "Emitida" não garante crédito efetivo |
| **Status "Benefícios Sociais CAIXA"/"Caixa Tem"** | Consulta digital (Caixa) | Pode indicar "crédito bloqueado" mesmo após processamento — divergência de fontes |
| **Protocolo de reclamação (ex.: "REQ...")** | Abertura de chamado | Sem prazo claro de resolução nem atualização proativa |
| **Comprovante de saque/extrato** | Pós-crédito efetivo | Só gerado depois do problema — não diagnostica bloqueios |
| **Senha Cidadão (6 dígitos)** | Autenticação em URA/apps/sites | Cadastro/recadastro combina telefone + presença física em lotérica |
| **Mensagens de erro genéricas no app** | Status divergente | "Procure um posto de atendimento" — sem causa raiz nem direcionamento |
| **Calendário de pagamento** | Portal Emprega Brasil/app | Referência "oficial", mas pode não bater com apps da Caixa |
| **Mensagem de bloqueio de Senha Cidadão por tentativas** *(Auditoria v1 — Falha 4)* | Durante autenticação na URA, após N tentativas | Texto exato e caminho de desbloqueio não confirmados — **ponto em aberto crítico** (Seção 8) |
| **Aviso de prazo de 67 dias para saque/devolução ao FAT** *(Auditoria v1 — Falha 2)* | Deveria constar no calendário de pagamento | Não há confirmação de comunicação proativa — risco de "perda silenciosa" do direito |
| **Coleta de CPF/NIS/Senha — sob a LGPD** *(Auditoria v1 — Falha 3a)* | Etapa de autenticação | Ver normativo LGPD (Seção 6.8); regras operacionais de TTS permanecem pendentes |

---

## 3. Frontstage (Atores Visíveis ao Cidadão)

Sem alterações relevantes em relação à v2 — a Auditoria v2 não questionou esta camada.

| Ator | Papel | Autonomia/preparo (observado/inferido) |
|---|---|---|
| **URA "Caixa Cidadão" (0800 726 0207)** | Primeiro contato; consultas via integração com SISGR/MTE; direciona para outros canais | Opera com regras + provável integração API/TTS (Seção 1, Jornada C); não resolve divergências entre sistemas |
| **Atendente humano Caixa Cidadão** | Pós-menu, horário comercial estendido | Informa status, orienta; sem alçada sobre questões do MTE; pode abrir chamados internos |
| **Central Alô Trabalho (158 — MTE)** | Solicitação, agendamento SRTE/SINE, CTPS Digital, CAGED | Acessa base "oficial" de habilitação; em relatos, contradisse informação da Caixa |
| **Apps/chat (Caixa Tem, Benefícios Sociais Caixa, site)** | Canal digital alternativo | Avaliações de usuários historicamente baixas (1,3–4,1/5) |
| **Canal PcD (0800 726 2492)** | Acessível 24h (auditiva/fala) | Existência confirmada; integração com fluxo de Seguro-Desemprego não confirmada |
| **Atendente de agência física** | Última instância; também **ponto de desbloqueio de Senha Cidadão** (cadastro inicial confirmado; bloqueio por tentativas — Seção 8, item 12) | Frequentemente vira canal de última instância mesmo para questões "remotas" |
| **Casa lotérica (rede credenciada)** | Ponte física obrigatória no cadastro/recadastro de senha e saques via Cartão Cidadão | — |
| **Posto SINE/SRTE** | Canal presencial de requerimento/agendamento via 158 | Vinculado ao MTE; destino final comum de quem começou ligando para a Caixa |

---

## 4. Backstage (Atores e Processos Fora da Visibilidade do Cidadão)

Estrutura da v2 mantida — **Auditoria v2, item 2: "Falha v1 resolvida... manter a estrutura consolidada"**. Itens 1–9 (v1) + item 4-bis (v2) preservados sem alteração:

1. **Pré-triagem (MTE/rede credenciada):** agente credenciado confere dados do RSD no momento do requerimento.
2. **Triagem automatizada (cruzamento de bases — MTE):** cruzamento do RSD com eSocial, CAGED/RAIS, Receita Federal — valida dispensa sem justa causa, vínculos e tempo de contribuição.
3. **Habilitação (MTE):** decisão sobre elegibilidade, número de parcelas e valores — **único ponto onde a tabela unificada da Seção 6.2 é efetivamente aplicada e calculada** para uma nova solicitação (reforça Jornada C, item 2).
4. **Processamento de pagamento (Caixa, Agente Pagador):** recebe determinação de pagamento (lotes) do FAT/MTE; credita em conta informada, conta Caixa, Conta Poupança Social Digital (Caixa Tem) ou Cartão Cidadão.
   - **4-bis. Conciliação de retorno/rejeição de crédito e devolução ao FAT:** quando o crédito não é efetivado (conta encerrada, dados incorretos, divergência de titularidade, falha sistêmica como junho/2025), o valor retorna à Caixa. Resolução CODEFAT 957/2022: **67 dias** de disponibilidade para saque, após os quais o valor não sacado é devolvido ao FAT. Gera provável status interno "retornado/pendente de reprocessamento", não confirmadamente visível ao cidadão.
5. **Equipe de incidentes/operações de transferência (Caixa):** incidente sistêmico de junho/2025 (atraso geral em transferências para outros bancos) — comunicação ao cidadão (via Reclame Aqui) chegou depois e por canal diferente do status do app. **Provavelmente alimenta o item 4-bis em volume anormal** quando ocorre.
6. **Auditoria/controle de fraude e suspensão automática:** novo vínculo registrado (eSocial/RAIS) → suspensão automática (não cancelamento), bloqueio efetivo em **5–15 dias**.
7. **Gestão de reclamações/Ouvidoria:** Reclame Aqui (Caixa atua oficialmente) + Ouvidoria MTE (0800 702 1111) — escalonamento backstage.
8. **Gestão de exceções normativas regionais:** ex. Resolução CODEFAT/MTE nº 1.036/2026 (parcelas adicionais para municípios de MG) — processo de atualização de regras por geografia/período, propagado a sistemas de habilitação e, presumivelmente, à base de conhecimento da URA (risco — fail point relacionado na Seção 7).
9. **Fluxo de informação Caixa↔MTE:** sincronização não confirmada como tempo real — divergências de status sugerem defasagem ou múltiplas "visões" dos mesmos dados (Seção 8).

---

## 5. Processos de Suporte (Infraestrutura Técnica e Operacional)

| Sistema/Infraestrutura | Função aparente | Operador |
|---|---|---|
| **SISGR (sisgr.caixa.gov.br)** | Consulta de habilitação/situação via portal "Cidadão Caixa" | Caixa (interface), dados de origem MTE |
| **Carteira de Trabalho Digital (app + base)** | Canal principal de requerimento/acompanhamento | MTE |
| **Portal Emprega Brasil / Gov.br** | Requerimento e consulta; integra CTPS digital | MTE |
| **Sistema de habilitação/triagem do Seguro-Desemprego** | Avalia carência e **parcelas (Seção 6.2)**; cruza eSocial/CAGED/RAIS | MTE |
| **eSocial / CAGED / RAIS** | Bases de vínculos — validam dispensa e detectam novo vínculo (gatilho de suspensão) | Governo Federal (Receita/MTE) |
| **App "Caixa Trabalhador"** | Consulta de habilitação, calendário, valores | Caixa |
| **App "Benefícios Sociais CAIXA"** | Consulta unificada de benefícios sociais | Caixa |
| **App "Caixa Tem"/Conta Poupança Social Digital** | Recebimento do crédito (Lei nº 14.075/2020) | Caixa |
| **Cartão Cidadão + Senha Cidadão (6 dígitos)** | Autenticação em autoatendimento + saque | Caixa, com confirmação presencial em lotéricas |
| **URA "Caixa Cidadão" (0800 726 0207)** | Atendimento eletrônico 24h + humano em horário estendido | Caixa |
| **Central Alô Trabalho (158)** | Solicitação, agendamento, CTPS Digital, CAGED | MTE |
| **0800 726 2492** | Atendimento acessível (PcD), 24h | Caixa |
| **Reclame Aqui (canal oficial Caixa)** | Reclamações públicas com respostas institucionais | Caixa |
| **Ouvidoria do MTE (0800 702 1111)** | Reclamações/denúncias sobre o MTE | MTE |
| **FAT (Fundo de Amparo ao Trabalhador)** | Fonte de recursos; destino de devoluções (67 dias) | Gestão tripartite (CODEFAT) |
| **Sistema antifraude de bloqueio de Senha Cidadão por tentativas** | Bloqueia credenciais após N tentativas incorretas de PIN | Caixa — canal de desbloqueio **não confirmado** (Seção 8, item 12) |
| **Processo de conciliação/devolução ao FAT (67 dias)** | Reconcilia créditos não efetivados/não sacados | Caixa (Agente Pagador) → FAT |
| **Arcabouço LGPD (Lei nº 13.709/2018)** | Princípios de tratamento de dados pessoais coletados via URA | Caixa e MTE como agentes de tratamento; regras operacionais de TTS não públicas |
| **Instrumento Caixa–FAT/MTE (Agente Pagador) — SLAs de atendimento** *[refinado — Auditoria v2 item 5]* | Presumível instrumento regendo obrigações/SLAs da Caixa na operação do canal | **Pendente** — candidato mais provável: **Termo de Execução Descentralizada (TED)** entre MTE/FAT e Caixa, ou disciplina equivalente dentro/anexa à Resolução CODEFAT 957/2022; conteúdo específico não localizado em fontes abertas |

**Limitações técnicas conhecidas (mantidas da v1/v2):** falta de visão unificada Caixa-MTE; latência de 5–15 dias na suspensão por novo vínculo; dependência de canais físicos para etapas de segurança; falhas sistêmicas em lote (jun/2025); dependências externas eSocial/CAGED/RAIS/Receita. A "falta de visão unificada" também explica, em parte, por que o processo de conciliação/devolução (item 4-bis) pode não ser exposto ao cidadão como status distinto.

---

## 6. Normativos, Regras e Critérios Relevantes

### 6.1 Base legal geral
- **Lei nº 7.998/1990** (com alterações da **Lei nº 8.900/1994** e, principalmente, da **Lei nº 13.134/2015** — conversão da MP 665/2014): institui o Programa do Seguro-Desemprego, o Abono Salarial e o FAT; base da atuação da Caixa como Agente Pagador.
- **Lei nº 14.075/2020**: permite pagamento de benefícios sociais (incl. Seguro-Desemprego) via Conta Poupança Social Digital (Caixa Tem).
- **Resolução CODEFAT nº 957/2022**: consolida normas de concessão, processamento e pagamento (revoga, entre outras, a Resolução CODEFAT nº 467/2005); regula trabalhador formal, doméstico, pescador artesanal, trabalhador resgatado e Bolsa de Qualificação Profissional em um único ato; define a janela de **67 dias** para devolução ao FAT.
- **Resolução CODEFAT/MTE nº 1.036/2026**: exemplo de norma de exceção regional (parcelas adicionais para municípios de MG).
- **Lei nº 13.709/2018 (LGPD)**: aplicável ao tratamento de CPF, NIS e dados financeiros no canal de atendimento — ver Seção 6.8.

### 6.2 Tabela unificada — Carência (elegibilidade) × Número de Parcelas, por número de solicitação **[Reescrita integral — Auditoria v2, item 1]**

Esta seção substitui integralmente a tabela genérica "6–11=3, 12–23=4, 24–36=5" das versões anteriores, que a Auditoria v2 corretamente identificou como **incorreta quando aplicada sem considerar o número de solicitação**. A base legal é o **art. 3º, I** (carência) e o **art. 4º, §2º, incisos I a III** (parcelas) da **Lei nº 7.998/1990, na redação dada pela Lei nº 13.134/2015**, com o **§3º** definindo que **fração de trabalho ≥ 15 dias conta como mês integral**.

> **Importante para o blueprint:** carência e parcelas usam janelas de referência **diferentes** — a carência é avaliada em uma janela curta e específica por solicitação (18, 12 ou "cada um dos 6" meses imediatamente anteriores), enquanto as parcelas são calculadas sobre o **tempo total de vínculo nos 36 meses anteriores à dispensa** (vedado contar vínculos já usados em período aquisitivo anterior). Por isso, **um trabalhador só pode estar na faixa de "3 parcelas" se, ao mesmo tempo, atender à carência da sua respectiva solicitação** — não são tabelas independentes.

| Nº da solicitação | Carência (elegibilidade — Art. 3º, I) | Tempo de vínculo nos 36 meses (referência para parcelas — Art. 4º, §2º) | Parcelas |
|---|---|---|---|
| **1ª solicitação** | Pelo menos **12 meses nos últimos 18 meses** imediatamente anteriores à dispensa | 12 a 23 meses | **4 parcelas** |
| | | 24 meses ou mais | **5 parcelas** |
| | | *(Não existe a hipótese de 3 parcelas na 1ª solicitação — o mínimo de carência, 12 meses, já posiciona o trabalhador na faixa de 4 ou 5 parcelas.)* | |
| **2ª solicitação** | Pelo menos **9 meses nos últimos 12 meses** imediatamente anteriores à dispensa | 9 a 11 meses | **3 parcelas** |
| | | 12 a 23 meses | **4 parcelas** |
| | | 24 meses ou mais | **5 parcelas** |
| **3ª solicitação em diante** | **Cada um dos 6 meses imediatamente anteriores à dispensa** (trabalho contínuo, sem lacunas, nos últimos 6 meses) | 6 a 11 meses | **3 parcelas** |
| | | 12 a 23 meses | **4 parcelas** |
| | | 24 meses ou mais | **5 parcelas** |

> **§3º (Lei nº 13.134/2015):** fração de trabalho igual ou superior a 15 dias é considerada mês integral para os efeitos desta tabela.

**Implicações operacionais (consolidando os fail points #14 e novo #15 da Seção 7):**
- Um sistema/atendente que aplique a faixa "6–11 meses → 3 parcelas" a um cidadão na **1ª solicitação** comete um **erro duplo**: (i) essa faixa não existe para 1ª solicitação; e (ii) um cidadão com 6–11 meses de vínculo **não atende à carência da 1ª solicitação** (precisa de 12) — ou seja, **não tem direito a nenhuma parcela**, não a "3 parcelas". Informar "3 parcelas" nesse cenário cria uma expectativa de direito **completamente falsa**, exatamente como apontado na Auditoria v2.
- A tabela deve ser **parametrizada por número de solicitação como primeira dimensão**, e só então cruzada com o tempo de vínculo — nunca o inverso.

### 6.3 Bolsa de Qualificação Profissional (modalidade distinta — mantida da v2)

Regida pelo **art. 2º-A da Lei nº 7.998/1990** e pela Resolução CODEFAT nº 957/2022, com tabela baseada em **dias** de período de desemprego/suspensão — **não se aplica** ao trabalhador formal/doméstico dispensado sem justa causa (que segue a Seção 6.2):

| Dias de desemprego/suspensão | Parcelas |
|---|---|
| 30 a 44 dias | 1 |
| 45 a 74 dias | 2 |
| 75 a 104 dias | 3 |
| 105 a 134 dias | 4 |
| 135 a 164 dias | 5 |

### 6.4 Prazos para requerer (mantido — divergência não resolvida)
- **Trabalhador formal:** majoritariamente 7º a 120º dia após a demissão (uma fonte minoritária de 2026 diverge para 90 dias) — **ver Seção 8**.
- **Trabalhador doméstico:** 7º a 90º dia.
- **Trabalhador resgatado:** até o 90º dia a contar do resgate.
- **Perda do prazo:** sistema "trava" a solicitação; reversão só por erro comprovado do sistema ou decisão judicial.

### 6.5 Valores do benefício (mantido)
- Cálculo pela média dos 3 últimos salários antes da dispensa, por tabela de faixas reajustada anualmente.
- Piso = salário mínimo vigente; teto por tabela (ex.: R$ 2.424,11 em 2025; R$ 2.518,65 em 2026, conforme fontes consultadas).
- Pagamento a cada 30 dias, contínuo ou alternado.

### 6.6 Suspensão, cancelamento e devolução (mantido + 67 dias)
- **Suspensão automática** por novo vínculo (eSocial/RAIS): bloqueio em 5–15 dias.
- **Cancelamento** por justa causa (salvo reversão judicial).
- **Devolução ao FAT** após 67 dias de disponibilização sem saque (Resolução CODEFAT 957/2022) — ver Backstage item 4-bis.

### 6.7 Canais formais (mantido)
- Portal Gov.br; app Carteira de Trabalho Digital; SRTE/SEPRT/SINE/postos credenciados (agendamento via 158); para consulta: apps Caixa Trabalhador e Benefícios Sociais CAIXA, Portal Cidadão Caixa (SISGR), 0800 726 0207.

### 6.8 LGPD — Lei nº 13.709/2018 **[mantido, linguagem fortalecida — Auditoria v2, item 4]**

Aplica-se a todo o fluxo de atendimento da URA (coleta/tratamento de CPF, NIS/PIS, validação por Senha Cidadão para acesso a dados financeiros):
- **Finalidade e adequação** (art. 6º, I e II): dados coletados devem se limitar ao necessário para autenticação e consulta;
- **Segurança e prevenção** (art. 6º, VII–VIII; art. 46): fundamento legal para exigência de Senha Cidadão antes de informações financeiras detalhadas;
- **Base legal provável**: cumprimento de obrigação legal/execução de política pública (art. 7º, II e III).

> **Pendência reforçada [Auditoria v2, item 4]:** os limites operacionais exatos do TTS da URA (o que pode ser verbalizado autonomamente vs. o que exige Senha Cidadão/validação humana/presencial) **não derivam diretamente da LGPD** — a LGPD fornece princípios, não um roteiro operacional. A Auditoria v2 confirma que esse detalhamento depende de **regulamentos internos de segurança da informação e governança de dados MTE-Caixa**, e que **não é alcançável via pesquisa em fontes abertas primárias** — esta não é uma lacuna de esforço de pesquisa, e sim uma característica do tipo de informação (interna/classificada). Tratado como pendente permanente na Seção 8, exceto se houver acesso institucional direto (ex.: entrevista com a área de SI da Caixa).

---

## 7. Fail Points Conhecidos, Prováveis ou Recorrentes

Os 11 fail points originais da v1 são mantidos integralmente (não contestados em nenhuma auditoria):

1. Canal "errado" para iniciar o processo (0800 726 0207 não é canal de requerimento).
2. Quedas de ligação antes do atendente humano, sem callback.
3. Divergência de status entre sistemas (Caixa vs. MTE/CTPS Digital).
4. "Empurra-empurra" institucional Caixa ⇄ MTE.
5. Mensagens de erro genéricas e não-acionáveis.
6. Dependência de etapa presencial mesmo em processos "digitais" (cadastro de Senha Cidadão).
7. Falhas sistêmicas em lote, com comunicação defasada (incidente jun/2025).
8. Janela de 5–15 dias para suspensão por novo vínculo (pagamentos "a mais" não reconciliados — mecanismo não confirmado).
9. Regras de exceção regionais/temporais potencialmente não refletidas na URA.
10. Improvisos do cidadão (múltiplos números, ida à agência, Reclame Aqui como "atalho", saque via lotérica por orientação informal).
11. Acessibilidade (canal PcD 0800 726 2492 sem confirmação de integração ao fluxo específico).

Fail points incorporados nas v1→v2 (mantidos):

12. **Bloqueio de Senha Cidadão por excesso de tentativas (DTMF/"fat finger") [Auditoria v1 — Falha 4; formalizado — Auditoria v2 item 3].** Cidadão com senha válida, mas bloqueado por erro de digitação repetido durante a autenticação na URA. **Status v3: ruptura confirmada, porém com caminho de resolução INDETERMINADO** — o blueprint deve representar este ramo sem assumir desfecho remoto ou presencial, até investigação empírica (Seção 8, item 12). Esta é, dos fail points mapeados, a que apresenta **maior risco de severidade subestimada**, pois pode transformar uma consulta de rotina em uma ruptura total do canal remoto.

13. **Retorno/rejeição de crédito não reconciliado, janela de 67 dias até devolução ao FAT [Auditoria v1 — Falha 2].** Parcela "emitida" que não chega à conta por problema bancário entra em janela de até 67 dias "invisível" nos status disponíveis, podendo culminar em perda do direito àquela parcela específica.

14. **Confusão entre modalidades do benefício (trabalhador formal/doméstico vs. Bolsa de Qualificação Profissional) ao informar número de parcelas [decorrente da correção da Falha 1, v2].** Se a tabela de "1–5 parcelas por dias" (Seção 6.3) for aplicada a um trabalhador formal, ou vice-versa, o cidadão recebe informação objetivamente incorreta.

**Novo fail point (v3):**

15. **Confusão entre as faixas de parcelas por número de solicitação, especialmente aplicação da faixa "3 parcelas" a um cidadão na 1ª solicitação [novo — Auditoria v2, item 1].** Conforme detalhado na Seção 6.2, a faixa "6–11 meses → 3 parcelas" só existe a partir da 3ª solicitação (com limiar de 9–11 meses na 2ª). Se um atendente ou sistema de retaguarda aplicar essa faixa a um cidadão na 1ª solicitação com 6–11 meses de vínculo, o erro é **duplo e mais grave que uma simples informação errada de quantidade**: o cidadão **não atende à carência da 1ª solicitação** (precisa de 12 meses) e, portanto, **não tem direito a nenhuma parcela** — informar "3 parcelas" cria uma expectativa de direito totalmente inexistente, com potencial de gerar reclamações formais por "não recebimento de benefício que foi prometido por atendente da Caixa".

---

## 8. Pontos que Seguem em Aberto

### 8.1 Itens resolvidos cumulativamente (registro histórico, para não serem reabertos)
- ✅ Carência da 3ª solicitação em diante = "cada um dos 6 meses imediatamente anteriores", contínuo, sem lacunas (resolvido na v2, confirmado — Auditoria v1).
- ✅ Tabela completa de carência × parcelas por número de solicitação (1ª/2ª/3ª+), incluindo a inexistência da faixa "3 parcelas" na 1ª solicitação (**resolvido nesta v3 — Auditoria v2, item 1**).
- ✅ Inferência sobre limitação tecnológica da URA na Jornada C — corrigida para base estrutural/temporal, não tecnológica (resolvido na v2, confirmado sem ressalvas — **Auditoria v2, item 6**).
- ✅ Processo de conciliação/devolução de crédito (67 dias) — incorporado e validado (**Auditoria v2, item 2**).

### 8.2 Itens que permanecem em aberto

1. **Árvore de menus real da URA (0800 726 0207):** estrutura exata de opções, reconhecimento de voz vs. DTMF, ponto exato da autenticação. *Resolução: ligação de teste real (shadowing).*
2. **Prazo de requerimento — 90 vs. 120 dias para trabalhador formal:** maioria das fontes aponta 120, uma fonte de 2026 diverge para 90. *Resolução: validar em fonte primária (texto consolidado do art. 3º ou normativo correlato do CODEFAT).*
3. **Mecanismo de sincronização Caixa↔MTE:** tempo real via API vs. réplica/batch com defasagem — não confirmado; as divergências de status sugerem defasagem, mas o mecanismo exato é desconhecido.
4. **Mecanismo de "pagamentos a mais" durante a janela de 5–15 dias de suspensão por novo vínculo:** não confirmado se há cobrança/compensação posterior ou ausência de reconciliação — distinto do mecanismo de devolução de 67 dias (que trata de outro gatilho).
5. **Comunicação de exceções normativas regionais (ex.: Resolução 1.036/2026) na URA:** não há evidência sobre como/se essas variações são propagadas ao script da URA.
6. **Existência de gravação de chamadas, pesquisa de satisfação pós-atendimento, ou notificações proativas (SMS):** sem evidência pública específica para este fluxo.
7. **Operação do 0800 726 0207 — equipe própria Caixa vs. terceirizada:** não confirmado; relevante para entender autonomia/treinamento/KPIs dos atendentes.
8. **Integração entre Reclame Aqui (canal oficial Caixa) e o atendimento telefônico:** não está claro se geram protocolo único rastreável entre canais.
9. **Volume relativo de chamadas sobre Seguro-Desemprego vs. outros assuntos no mesmo 0800:** dado de 250 mil ligações/dia é de ~2012 e não segmentado.
10. **Critérios e processo de escalonamento interno** (para onde vai um caso de "crédito bloqueado sem explicação", e SLA esperado).
11. **Limites operacionais de verbalização via TTS na URA (LGPD/segurança da informação) [Auditoria v2, item 4 — confirmado fora do alcance de fontes abertas]:** pendência permanente, salvo acesso institucional direto às normas internas de SI da Caixa/MTE.
12. **Caminho de desbloqueio da Senha Cidadão por excesso de tentativas (remoto vs. presencial) [Auditoria v2, item 3 — ponto crítico]:** **item de maior prioridade para validação empírica** antes da finalização do blueprint, dado seu potencial de transformar uma ruptura temporária em ruptura total do canal remoto. *Resolução: (i) ligação de teste deliberadamente errando a senha repetidas vezes; ou (ii) consulta direta à documentação/área responsável da Caixa sobre os dois fluxos distintos ("recadastrar senha" vs. "desbloquear por tentativas").*
13. **Existência e conteúdo do instrumento Caixa–FAT/MTE (Agente Pagador) com SLAs de atendimento [Auditoria v2, item 5 — refinado]:** candidato mais provável é um **Termo de Execução Descentralizada (TED)** ou disciplina equivalente associada à Resolução CODEFAT 957/2022. *Resolução: pedido via LAI ao MTE/CODEFAT e/ou à Caixa, especificamente pelo TED (ou instrumento correlato) vigente para a operação de Agente Pagador do Seguro-Desemprego, incluindo eventuais cláusulas de atendimento ao cidadão.*
14. **Se a URA/atendentes distinguem, na prática, entre as modalidades "trabalhador formal/doméstico" e "Bolsa de Qualificação Profissional"** ao informar número de parcelas (fail point #14) — sem evidência pública; relevante apenas se Bolsa de Qualificação Profissional for público relevante deste serviço.

---

## Anexo — Fontes adicionais consultadas nesta v3

- Texto integral do **art. 4º, §2º, incisos I, II e III, e §3º, da Lei nº 7.998/1990**, na redação dada pela **Lei nº 13.134/2015** (Planalto, ANTT, e fontes secundárias consistentes — Jusbrasil, Pontotel, VGRA Jurídico), confirmando a tabela unificada da Seção 6.2.
- Confirmação cruzada de múltiplas fontes secundárias sobre a relação entre número de solicitação, carência e número de parcelas (Convenia, Exponencial/Creditas, Jusbrasil, IPEA).
- Fontes da v1/v2 permanecem válidas e não foram recontestadas pela Auditoria v2 (ver anexos das versões anteriores).

---

## Resumo executivo — estado final da pesquisa

A v3 fecha o ciclo de auditoria com **todos os 6 itens da Auditoria v2 endereçados**: 1 corrigido integralmente (reescrita da tabela de carência/parcelas — a correção mais substancial de todo o processo), 1 confirmado como já resolvido (conciliação/devolução), 1 formalizado como ruptura crítica sem resolução mapeada (bloqueio de senha), 1 mantido como pendência permanente com justificativa reforçada (LGPD/TTS), 1 refinado com alvo de busca mais específico (Convênio/TED MTE-Caixa), e 1 confirmado como corretamente resolvido sem ação adicional (inferência tecnológica da URA).

A pesquisa está pronta para sustentar a construção do Service Blueprint AS-IS, com **dois pontos em aberto priorizados para validação empírica antes da finalização**: (i) o caminho de desbloqueio da Senha Cidadão por tentativas (item 8.2.12) e (ii) a árvore de menus real da URA (item 8.2.1) — ambos exigem ligação de teste real, não pesquisa documental adicional.
