# Pesquisa AS-IS — Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal

## Nota metodológica

Este documento foi construído a partir de pesquisa em fontes públicas: páginas oficiais da Caixa Econômica Federal e do Ministério do Trabalho e Emprego (MTE), legislação e resoluções do CODEFAT, reportagens institucionais sobre os canais de atendimento, e relatos de cidadãos em plataformas de reclamação (Reclame Aqui) sobre o serviço de Seguro-Desemprego. Não houve acesso direto à URA (não foi possível "discar" e mapear a árvore de menus em tempo real), então a estrutura interna do IVR foi inferida a partir da documentação dos serviços oferecidos pelo canal e de relatos de usuários. Todos os pontos que dependem dessa inferência estão marcados como **hipótese** e listados na Seção 8.

Um achado estrutural relevante para todo o restante da pesquisa: **a Caixa não é a gestora do benefício Seguro-Desemprego — ela atua apenas como "Agente Pagador"**, com recursos do FAT (Fundo de Amparo ao Trabalhador), nos termos da Lei nº 7.998/1990. A gestão, análise, habilitação e concessão do benefício são de responsabilidade do Ministério do Trabalho e Emprego (MTE), por meio da rede SINE/SRTE e dos sistemas federais (Carteira de Trabalho Digital, Portal Emprega Brasil). Essa divisão de responsabilidades é o pano de fundo de praticamente todos os gargalos identificados: a URA da Caixa atende ligações sobre um benefício cuja "fonte da verdade" (elegibilidade, parcelas, bloqueios) está, em grande parte, fora do controle direto da Caixa.

---

## 1. Jornada do Cidadão (Passo a Passo)

A "Atendimento ao Seguro-Desemprego pela URA" não é uma jornada única — na prática, o cidadão chega à URA da Caixa (0800 726 0207, "Caixa Cidadão") com diferentes intenções, que se misturam porque o canal telefônico é compartilhado com PIS, FGTS, Cartão Social e outros benefícios sociais. Vale mapear pelo menos três variações de jornada.

### 1.1 Jornada A — Cidadão tenta solicitar o benefício (primeira vez)

1. **Gatilho:** o trabalhador foi demitido sem justa causa e recebeu (ou não) o "Requerimento do Seguro-Desemprego" do empregador.
2. **Primeiro contato:** ao buscar informação sobre "como dar entrada no seguro-desemprego", o cidadão frequentemente liga primeiro para o 0800 726 0207 (Caixa Cidadão), por ser o número mais divulgado/lembrado associado à Caixa e a benefícios sociais.
3. **Ponto de decisão 1 — Desvio de canal:** a URA da Caixa, ao identificar que o assunto é "solicitação" (e não "consulta de pagamento"), tende a informar que o requerimento **não é feito pela Caixa**, e sim pelo aplicativo "Carteira de Trabalho Digital", pelo Portal Gov.br/Emprega Brasil, ou presencialmente em postos do SINE/SRTE (mediante agendamento pela central 158).
4. **Bifurcação:**
   - **Caminho 1 (digital):** o cidadão é orientado a baixar/usar o app Carteira de Trabalho Digital. Aqui a jornada telefônica com a Caixa **termina sem resolução** — o cidadão é redirecionado para outro canal, de outro órgão, com login próprio (conta Gov.br).
   - **Caminho 2 (presencial):** o cidadão liga para o 158 (Alô Trabalho/MTE) para agendar atendimento presencial em uma SRTE/SINE. Isso introduz um **segundo canal telefônico**, com horários e filas próprios (158 funciona de segunda a sábado, 7h–19h).
5. **Ponto de ruptura comum:** o cidadão que liga para a Caixa esperando "resolver o seguro-desemprego" sai da ligação sem ter avançado seu pedido — apenas com uma indicação de "para onde ir". Se o cidadão não tem smartphone, dados móveis ou conta Gov.br validada, essa orientação pode ser inviável na prática, criando um **loop**: sem conseguir abrir o app, ele liga novamente para a Caixa, recebe a mesma orientação, e assim por diante.
6. **Conclusão "de sucesso" desta jornada:** o cidadão consegue, em outro canal (app/posto SINE), formalizar o requerimento. A partir daqui ele entra na Jornada B (acompanhamento).

### 1.2 Jornada B — Cidadão liga para consultar status/parcela já solicitada

1. **Gatilho:** o cidadão já deu entrada no benefício e quer saber se foi aprovado ("habilitado"), quantas parcelas terá direito, quando a próxima parcela cai, ou por que uma parcela não foi paga.
2. **Primeiro contato:** liga para 0800 726 0207 (Caixa Cidadão), disponível em atendimento eletrônico 24h/dia, 7 dias por semana; atendimento humano de segunda a sábado (faixas de horário variam entre 8h–21h/22h nos dias úteis e 10h–16h no sábado, conforme a fonte).
3. **Autenticação na URA (hipótese, ver Seção 8):** o sistema solicita CPF e/ou NIS/PIS, possivelmente seguido de senha numérica de 6 dígitos (a mesma "Senha Cidadão" usada no Cartão Cidadão e em outros canais de benefícios sociais).
4. **Ponto de decisão 2 — Cidadão não possui a senha cadastrada:** se o cidadão nunca cadastrou a Senha Cidadão (comum entre quem nunca usou Cartão Cidadão antes), a URA pode não conseguir autenticá-lo para uma consulta detalhada. O cadastro de senha por telefone existe, mas exige uma etapa presencial complementar (ir a uma casa lotérica após ~2 horas da ligação para confirmar o cadastro) — ou seja, **mesmo o processo de "se cadastrar para usar o telefone" depende de presença física**.
5. **Consulta bem-sucedida:** se autenticado, o sistema informa dados como situação do benefício, data prevista de crédito, valor da parcela. Esses dados, segundo a própria Caixa em respostas a reclamações, refletem informações que vêm de **outro sistema** (gerido pelo MTE) — ou seja, a URA é uma interface de consulta sobre uma base que não é "dela".
6. **Ponto de ruptura comum — Discrepância entre canais:** é frequente o cidadão encontrar status diferentes em canais diferentes no mesmo dia (ex.: app "Carteira de Trabalho Digital" mostra "parcela emitida", app "Caixa Tem"/"Benefícios Sociais Caixa" mostra "crédito bloqueado", e a URA/atendente da Caixa pode informar que "não há pendência"). O cidadão não tem como saber qual fonte está correta, e a ligação pode terminar sem que o atendente consiga explicar a divergência — apenas orientando a "aguardar" ou "procurar uma agência".
7. **Ponto de ruptura comum — Queda de chamada:** relatos indicam que ligações para o atendimento "caem" (são interrompidas) antes de chegar a um atendente humano, especialmente em horários de pico, obrigando o cidadão a discar novamente e refazer toda a navegação no menu/autenticação.
8. **Escalonamento:** se a URA não resolve, o cidadão pode ser direcionado a: (a) atendente humano da Caixa Cidadão (se dentro do horário); (b) central 158/MTE; (c) agência física da Caixa; (d) canais digitais (chat do site, app); (e), em casos extremos, órgãos externos (Ouvidoria do MTE, Procon, Defensoria Pública), conforme indicado em reclamações públicas.

### 1.3 Jornada C — Cidadão liga para renovar/solicitar novamente o benefício (2ª, 3ª solicitação)

1. **Gatilho:** o trabalhador foi demitido novamente após período empregado e quer requerer o benefício outra vez.
2. **Diferença-chave:** as regras de carência mudam conforme o número de solicitações anteriores (ver Seção 6). A URA, sendo um sistema de respostas pré-gravadas/genéricas, **provavelmente não tem capacidade de avaliar a carência individual do cidadão** — ela pode, no máximo, informar a regra geral. A avaliação real (se o cidadão cumpre os meses mínimos trabalhados) é feita no sistema de habilitação do MTE durante o processamento do requerimento.
3. **Caminho:** semelhante à Jornada A — o cidadão é majoritariamente direcionado para o app Carteira de Trabalho Digital / Portal Emprega Brasil / posto SINE, e não consegue "renovar" pela URA da Caixa propriamente.
4. **Ponto de ruptura específico:** se o cidadão perdeu o prazo de 7 a 120 dias (ou 90 dias para trabalhador doméstico) após a demissão, o sistema "trava" a solicitação. A URA, ao confirmar essa informação, não tem alçada para reverter — a reversão exigiria erro comprovado do sistema ou decisão judicial, ou seja, está fora do alcance de qualquer canal de atendimento de rotina.

### 1.4 Jornada D — Cidadão tenta registrar reclamação formal

1. **Gatilho:** parcela não paga, bloqueio indevido, atendimento anterior insatisfatório.
2. **Caminho oficial divulgado:** o mesmo número 0800 726 0207 atende reclamações — "basta ligar e registrar a reclamação na opção desejada".
3. **Caminho alternativo (observado em reclamações públicas):** muitos cidadãos, frustrados com o telefone, recorrem a canais externos à Caixa — plataformas como Reclame Aqui, redes sociais, Procon, Ouvidoria do MTE (0800 702 1111) — o que sugere que **o canal telefônico não é percebido como eficaz para resolução de reclamações**, funcionando mais como um registro inicial do que como um canal de resolução.
4. **Ponto de ruptura:** respostas da Caixa em canais públicos frequentemente reiteram que a "gestão do benefício é do MTE" e que a Caixa atua apenas como pagadora — o que, da perspectiva do cidadão, é repassar a responsabilidade sem necessariamente resolver o problema concreto (ex.: dinheiro não creditado).

---

## 2. Evidências Físicas e Perceptíveis em Cada Etapa

| Evidência | Onde aparece | Qualidade/Clareza observada |
|---|---|---|
| **Requerimento do Seguro-Desemprego (RSD)** | Documento (físico ou eletrônico) entregue pelo empregador ao trabalhador demitido; pré-requisito para iniciar o processo | É o documento "chave" — sem ele, o processo não inicia. Hoje, parte das informações já está digitalizada via Carteira de Trabalho Digital, mas o documento em si ainda é mencionado como necessário em diversos guias |
| **Locução/menu da URA (Caixa Cidadão 0800 726 0207)** | Primeiro contato telefônico | Cobre múltiplos assuntos (PIS, Seguro-Desemprego, FGTS, Cartão Social, SIC, resultados de loterias) no mesmo número — potencial fonte de confusão sobre qual opção escolher (hipótese, ver Seção 8) |
| **Tempo de espera / fila (hold)** | Durante a tentativa de falar com atendente humano | Relatado como longo o suficiente para a ligação "cair" antes do atendimento — não documentado oficialmente quanto a tempo médio |
| **Status no app "Carteira de Trabalho Digital"** | Consulta digital (MTE) | Indica status como "emitida", mas não necessariamente reflete o crédito efetivo na conta |
| **Status no app "Benefícios Sociais CAIXA" / "Caixa Tem"** | Consulta digital (Caixa) | Pode indicar "crédito bloqueado" mesmo quando o pagamento já foi processado, segundo relatos e respostas da própria Caixa — gera divergência entre fontes |
| **Número de protocolo de reclamação (ex.: "REQ...")** | Gerado ao abrir um chamado/reclamação | Existe, mas cidadãos relatam não receber prazo claro de resolução nem atualização proativa |
| **Comprovante de saque / extrato (Cartão Cidadão, Caixa Tem)** | Após o crédito ser efetivamente disponibilizado | Documenta o recebimento, mas só é gerado *depois* do problema (não ajuda a diagnosticar bloqueios) |
| **Senha Cidadão (6 dígitos)** | Necessária para autenticação em canais de autoatendimento (URA, apps, sites) | O processo de cadastro/recadastro combina telefone + presença física em casa lotérica — uma evidência de que o canal "100% telefônico" não é, na prática, autossuficiente |
| **Mensagens de erro genéricas no app** ("qualquer dúvida, procure um posto de atendimento") | Quando o status diverge do esperado | Não fornece causa raiz nem direcionamento específico — empurra o cidadão de volta para outro canal |
| **Calendário de pagamento (gerado após habilitação)** | Disponível via Portal Emprega Brasil / app | É a referência "oficial" de datas, mas pode não bater com o que aparece nos apps da Caixa |

**Síntese da camada "Evidências Físicas":** as evidências disponíveis ao cidadão são fragmentadas entre, no mínimo, três ecossistemas (Caixa: apps e 0800 726 0207; MTE: Carteira de Trabalho Digital, Portal Emprega Brasil, 158; e o canal físico: agências Caixa, lotéricas, postos SINE). Não há uma evidência única e confiável que sirva como "fonte da verdade" visível ao cidadão.

---

## 3. Atores de Frontstage (Visíveis ao Cidadão)

| Ator | Papel na jornada | Nível de autonomia/preparo (observado ou inferido) |
|---|---|---|
| **URA / sistema automatizado "Caixa Cidadão" (0800 726 0207)** | Primeiro ponto de contato; presta informações gerais, possivelmente realiza consultas de status mediante autenticação; direciona para outros canais | Provavelmente opera com respostas roteirizadas/baseadas em regras; não parece ter acesso para *resolver* divergências entre sistemas — apenas informar o que está registrado |
| **Atendente humano da Caixa Cidadão** | Acionado após navegação no menu, dentro do horário de atendimento humano (seg-sáb) | Segundo respostas públicas da Caixa, parece limitado a informar status e orientar — não tem alçada para corrigir bloqueios que dependem do MTE; pode abrir chamados internos |
| **Central Alô Trabalho (158 — MTE)** | Canal alternativo/paralelo para solicitação, agendamento em SRTE/SINE e dúvidas sobre CTPS Digital, CAGED | Atua sobre a base "oficial" de habilitação — em relatos, conseguiu informar que um pagamento já havia sido processado pelo governo, contradizendo a Caixa |
| **Atendimento via app/chat (Caixa Tem, Benefícios Sociais Caixa, site Caixa)** | Canal digital alternativo, frequentemente sugerido como mais rápido que telefone | Qualidade percebida é baixa — os apps relacionados têm avaliações de usuários historicamente baixas (entre 1,3 e 4,1/5 dependendo do app e loja) |
| **Atendimento exclusivo PcD (0800 726 2492)** | Canal acessível 24h para pessoas com deficiência auditiva/de fala | Existência confirmada; não há dados sobre volume de uso ou integração com o fluxo de Seguro-Desemprego especificamente |
| **Atendente de agência física da Caixa** | Acionado quando o canal remoto não resolve (ex.: bloqueio de cartão, problemas de senha, "crédito bloqueado") | Often torna-se o canal de "última instância", mesmo para problemas que, em tese, deveriam ser resolvidos remotamente |
| **Casa lotérica (rede credenciada)** | Etapa intermediária no cadastro/recadastro de senha e em saques via Cartão Cidadão | Atua como "ponte" física obrigatória mesmo em processos iniciados por telefone |
| **Posto SINE / Superintendência Regional do Trabalho (SRTE)** | Canal presencial de requerimento/agendamento via 158 | Vinculado ao MTE, não à Caixa — mas é frequentemente o destino final de quem começou a jornada ligando para a Caixa |

---

## 4. Atores e Processos de Backstage (Fora da Visibilidade do Cidadão)

Com base na descrição oficial do fluxo (IBGE/MTE) e nas respostas institucionais da Caixa, o backstage provavelmente envolve:

1. **Equipe/sistema de pré-triagem (MTE/rede credenciada):** no momento do requerimento (presencial ou digital), há uma etapa de **pré-triagem**, em que um agente credenciado confere os dados informados no Requerimento do Seguro-Desemprego (RSD).
2. **Triagem automatizada (cruzamento de bases — MTE):** o sistema cruza as informações do RSD com bases de dados governamentais — isso provavelmente inclui **eSocial, CAGED/RAIS (vínculos empregatícios) e Receita Federal (CPF)**, para validar dispensa sem justa causa, vínculos anteriores e tempo de contribuição.
3. **Habilitação (MTE):** decisão sobre elegibilidade, número de parcelas e valores, com base nas regras de carência e na Resolução CODEFAT vigente.
4. **Processamento de pagamento (Caixa, como Agente Pagador):** a Caixa recebe a determinação de pagamento (lotes) do FAT/MTE e processa os créditos — em conta bancária informada (qualquer instituição), conta poupança Caixa, Conta Poupança Social Digital (Caixa Tem) ou Cartão Cidadão.
5. **Equipe de incidentes/operações de transferência (Caixa):** em pelo menos um caso documentado publicamente (junho de 2025), houve atraso sistêmico em transferências para contas de outros bancos, afetando "todas as instituições financeiras" — indicando uma área de operações bancárias que monitora e comunica falhas em lote, mas com defasagem em relação à comunicação ao cidadão (o status no app não refletia a explicação dada depois pela Caixa).
6. **Auditoria/controle de fraude e suspensão automática:** quando um novo vínculo empregatício é registrado (eSocial/RAIS), o sistema **suspende automaticamente** (não cancela) o benefício, com um intervalo relatado de **5 a 15 dias** entre o registro do vínculo e o bloqueio efetivo das parcelas restantes — uma janela em que parcelas podem ser pagas "indevidamente" e, presumivelmente, precisam ser tratadas depois (cobrança/compensação — não confirmado).
7. **Gestão de reclamações/Ouvidoria:** existe uma camada de atendimento via Reclame Aqui (a Caixa indicou recentemente atuar oficialmente na plataforma) e a Ouvidoria do MTE (0800 702 1111) — ambas operando como **escalonamento backstage** para casos não resolvidos nos canais primários.
8. **Gestão de exceções normativas regionais:** a existência de resoluções específicas do CODEFAT para situações regionais (ex.: Resolução CODEFAT/MTE nº 1.036/2026, concedendo parcelas adicionais a trabalhadores de municípios específicos de Minas Gerais afetados por crise local) implica um processo backstage de **atualização de regras de elegibilidade por geografia/período**, que precisa ser propagado a todos os sistemas de habilitação e, presumivelmente, à base de conhecimento da URA — um ponto de risco para desatualização do atendimento automatizado (hipótese).
9. **Fluxo de informação entre Caixa e MTE:** não há evidência pública detalhada sobre a frequência/latência de sincronização entre o sistema de habilitação do MTE e os sistemas de consulta da Caixa (apps, URA, sisgr.caixa.gov.br) — mas as divergências de status relatadas por usuários sugerem que essa sincronização **não é em tempo real**, ou que há múltiplas cópias/visões dos mesmos dados que nem sempre convergem.

---

## 5. Processos de Suporte (Infraestrutura Técnica e Operacional)

| Sistema/Infraestrutura | Função aparente | Operador |
|---|---|---|
| **SISGR (sisgr.caixa.gov.br)** | Sistema de consulta de habilitação/situação do Seguro-Desemprego acessado via portal "Cidadão Caixa" | Caixa (interface), dados de habilitação de origem MTE |
| **Carteira de Trabalho Digital (app + base)** | Canal principal hoje para requerimento e acompanhamento do benefício; substitui crescentemente o comparecimento presencial ao SINE | MTE |
| **Portal Emprega Brasil / Portal Gov.br** | Canal de requerimento e consulta; integra CTPS digital | MTE |
| **Sistema de habilitação/triagem do Seguro-Desemprego** | Avalia carência, elegibilidade, número de parcelas; cruza dados com eSocial/CAGED/RAIS | MTE (nome de sistema específico não confirmado — referido genericamente como "sistema Seguro-Desemprego" pelo IBGE) |
| **eSocial / CAGED / RAIS** | Bases de vínculos empregatícios usadas para validar dispensa sem justa causa e detectar novo vínculo (gatilho de suspensão automática) | Governo Federal (Receita Federal/MTE) |
| **App "Caixa Trabalhador"** | Consulta de habilitação, calendário de pagamento, valores das parcelas | Caixa |
| **App "Benefícios Sociais CAIXA"** | Consulta unificada de múltiplos benefícios sociais, incluindo Seguro-Desemprego, usando a mesma senha do app Trabalhador/FGTS | Caixa |
| **App "Caixa Tem" / Conta Poupança Social Digital** | Recebimento do crédito do benefício (uma das opções de conta), conforme Lei nº 14.075/2020 | Caixa |
| **Cartão Cidadão + Senha Cidadão (6 dígitos)** | Identificação/autenticação em canais de autoatendimento (URA, apps, sites) e saque em rede lotérica/ATM | Caixa, com etapa de confirmação presencial em lotéricas |
| **URA "Caixa Cidadão" (0800 726 0207)** | Atendimento eletrônico 24h + atendimento humano em horário comercial estendido; cobre PIS, Seguro-Desemprego, FGTS, Cartão Social, SIC | Caixa |
| **Central Alô Trabalho (158)** | Atendimento telefônico do MTE para solicitação, agendamento em SRTE/SINE, CTPS Digital, CAGED, legislação trabalhista | MTE |
| **0800 726 2492** | Atendimento acessível (PcD auditiva/de fala), 24h | Caixa |
| **Reclame Aqui (canal oficial da Caixa)** | Canal de atendimento de reclamações públicas, com respostas institucionais | Caixa (atuação recente confirmada) |
| **Ouvidoria do MTE (0800 702 1111)** | Canal de reclamações/denúncias sobre o MTE, incluindo Seguro-Desemprego | MTE |
| **FAT (Fundo de Amparo ao Trabalhador)** | Fonte de recursos do benefício | Gestão tripartite (CODEFAT) |

**Limitações técnicas conhecidas (a partir de evidências indiretas):**
- **Falta de visão unificada entre sistemas Caixa e MTE**, evidenciada por status divergentes entre apps no mesmo dia para o mesmo benefício.
- **Latência na propagação de bloqueios/desbloqueios**, com janela de 5 a 15 dias entre registro de novo vínculo e suspensão efetiva.
- **Dependência de canais físicos (lotéricas, agências) para etapas de segurança** (cadastro de senha, desbloqueio por segurança), mesmo quando o processo principal é remoto.
- **Falhas sistêmicas em lote de transferências bancárias** já ocorreram (junho de 2025), afetando pagamentos para contas de terceiros bancos, sem comunicação proativa imediata ao cidadão pelos canais de autoatendimento.
- **Dependências externas (MTE, Receita Federal via eSocial/CAGED/RAIS)**: qualquer atraso ou inconsistência nessas bases (ex.: vínculo registrado incorretamente, CPF com pendência) se propaga para a experiência do cidadão na Caixa, sem que a Caixa tenha, aparentemente, meios de corrigir a causa raiz.

---

## 6. Normativos, Regras e Critérios Relevantes

- **Lei nº 7.998, de 11 de janeiro de 1990:** institui o Programa do Seguro-Desemprego, o Abono Salarial e cria o FAT — base legal do benefício e da atuação da Caixa como Agente Pagador.
- **Lei nº 14.075/2020 (22/10/2020):** permite que pagamentos de benefícios sociais (Abono Salarial, Seguro-Desemprego, Bolsa Família, entre outros) sejam feitos via Conta Poupança Social Digital (app Caixa Tem).
- **Resolução CODEFAT nº 957, de 21 de dezembro de 2022:** define a tabela de número de parcelas conforme o tempo de desemprego/contribuição:
  - 1 parcela: 30 a 44 dias de trabalho no período de referência;
  - 2 parcelas: 45 a 74 dias;
  - 3 parcelas: 75 a 104 dias;
  - 4 parcelas: 105 a 134 dias;
  - 5 parcelas: 135 a 164 dias.
  - De forma geral, o benefício varia de **3 a 5 parcelas**, dependendo do tempo trabalhado nos últimos 36 meses e do número de solicitações anteriores. Para as 5 parcelas, normalmente é exigido mínimo de 24 meses trabalhados nos últimos 36 meses.
- **Resolução CODEFAT/MTE nº 1.036, de 3 de março de 2026:** exemplo de **norma de exceção regional** — concede 2 parcelas adicionais a trabalhadores dispensados entre 01/09/2025 e 31/03/2026 com vínculo em empregadores de Juiz de Fora, Matias Barbosa e Ubá (MG), provavelmente em razão de crise econômica/desastre local. Evidencia que **as regras de elegibilidade não são estáticas** e podem variar por município/período.

### Critérios de elegibilidade (regra geral)
O trabalhador deve, no momento do requerimento:
- Ter sido dispensado sem justa causa (inclui dispensa indireta), ou estar em uma das situações especiais (contrato suspenso por curso/programa de qualificação oferecido pelo empregador; pescador profissional em período de defeso; trabalhador resgatado de condição análoga à de escravo; trabalhador doméstico dispensado sem justa causa);
- Estar desempregado e sem renda própria para o sustento próprio e da família;
- Não estar recebendo outro benefício de prestação continuada da Previdência Social (exceto auxílio-acidente ou pensão por morte);
- Cumprir o período de carência (ver abaixo).

### Carência (tempo mínimo trabalhado)
- **1ª solicitação:** ao menos 12 meses trabalhados nos últimos 18 meses;
- **2ª solicitação:** ao menos 9 meses trabalhados nos últimos 12 meses;
- **3ª solicitação em diante:** ao menos 6 meses trabalhados (a formulação exata — "nos últimos 6 meses" vs. "antes da demissão, sem especificar janela" — varia entre fontes; ver Seção 8).

### Prazos para requerer
- **Trabalhador formal (regra majoritária nas fontes consultadas):** do 7º ao 120º dia após a demissão.
- **Trabalhador doméstico:** do 7º ao 90º dia após a demissão.
- **Trabalhador resgatado de condição análoga à escravidão:** até o 90º dia a contar do resgate.
- Uma fonte (2026) menciona "7 a 90 dias (não 120)" para a regra geral, divergindo das demais — tratado como ponto de incerteza (Seção 8).
- **Perda do prazo:** o sistema "trava" a solicitação; reversão só é possível em casos raros de erro comprovado do sistema ou decisão judicial.

### Valores do benefício
- Calculado com base na **média dos três últimos salários** recebidos antes da dispensa, segundo tabela de faixas reajustada anualmente pelo MTE/Codefat.
- **Piso:** equivalente ao salário mínimo vigente (ex.: R$ 1.518 em 2025; R$ 1.621 em 2026, segundo fontes consultadas).
- **Teto:** ex.: R$ 2.424,11 (2025) / R$ 2.518,65 (2026), conforme fontes consultadas.
- Pagamento a cada 30 dias, contínuo ou alternado conforme o número de parcelas.

### Suspensão e cancelamento
- **Suspensão automática (não cancelamento):** ocorre quando um novo vínculo empregatício é registrado no eSocial/RAIS, com bloqueio efetivo em **5 a 15 dias** após o registro.
- **Cancelamento/inelegibilidade:** dispensa por justa causa exclui o direito ao benefício (salvo reversão judicial da justa causa, que pode restituir o direito).
- **Bloqueio de crédito por dados bancários incorretos/incompletos:** a Caixa segue uma ordem de prioridade para tentar creditar — conta poupança Caixa identificada, depois conta poupança social digital, depois saque via canais alternativos (Cartão Cidadão/Senha Cidadão).

### Canais formais de requerimento, consulta e renovação (segundo a Caixa/MTE)
- Portal Gov.br;
- Aplicativo Carteira de Trabalho Digital (Android/iOS);
- Presencialmente nas Superintendências Regionais do Trabalho (SRTE), SEPRT, SINE e postos credenciados pelo MTE, mediante agendamento pela central 158;
- Para consulta (não para requerimento inicial): apps Caixa Trabalhador e Benefícios Sociais CAIXA, Portal Cidadão Caixa (sisgr), telefone 0800 726 0207.

---

## 7. Fail Points Conhecidos, Prováveis ou Recorrentes

1. **Canal "errado" para iniciar o processo:** o número mais lembrado/divulgado para assuntos de benefícios (0800 726 0207, Caixa) **não é o canal de requerimento** do Seguro-Desemprego — gerando, na melhor das hipóteses, um redirecionamento, e na pior, um loop entre canais para quem não consegue usar apps/portais digitais.
2. **Quedas de ligação ("as ligações sempre caem")**: relato recorrente de chamadas que são interrompidas antes de chegar a um atendente — provável gargalo de capacidade/fila em horários de pico, sem mecanismo relatado de retorno automático de chamada (callback).
3. **Divergência de status entre sistemas (Caixa vs. MTE/CTPS Digital):** o mesmo benefício pode aparecer como "emitido" em um canal e "crédito bloqueado" em outro, no mesmo dia — sem explicação imediata ao cidadão, e sem que o atendente da URA/humano pareça ter visibilidade da causa.
4. **"Empurra-empurra" institucional (Caixa ⇄ MTE):** cidadãos relatam ser informados pela Caixa que "a gestão é do MTE" e pelo MTE/158 que "o pagamento já foi feito pelo governo, o problema é da Caixa" — cada lado aponta para o outro, sem um responsável único e visível pela resolução ponta a ponta.
5. **Mensagens de erro genéricas e não-acionáveis:** quando há um problema (ex.: "crédito bloqueado"), o app frequentemente apenas orienta "procure um posto de atendimento", sem indicar qual posto, qual documentação levar, ou prazo esperado.
6. **Dependência de etapa presencial mesmo em processos "digitais":** cadastro/recadastro de Senha Cidadão por telefone exige confirmação física em casa lotérica horas depois — uma "gambiarra" estrutural que combina canal remoto com canal físico obrigatório.
7. **Falhas sistêmicas em lote, com comunicação defasada:** incidente de junho/2025 (atraso geral em transferências para outros bancos) mostra que falhas sistêmicas existem e que a explicação ao cidadão (via Reclame Aqui) chegou depois, e separadamente, do status exibido nos apps — ou seja, **não há um canal único e automático de "status de incidente"** acessível ao cidadão no momento da falha.
8. **Janela de 5–15 dias para suspensão por novo vínculo:** pode gerar tanto pagamentos "a mais" (que talvez precisem ser tratados depois — não confirmado) quanto confusão para o cidadão que já está empregado mas ainda recebe (ou deixa de receber abruptamente) parcelas.
9. **Regras de exceção regionais/temporais (ex.: Resolução 1.036/2026) potencialmente não refletidas na URA:** scripts de atendimento automatizado tendem a ser atualizados com defasagem em relação a resoluções pontuais do CODEFAT — risco de a URA fornecer informação desatualizada sobre número de parcelas para públicos específicos (hipótese).
10. **Improvisos do cidadão (gambiarras observadas em relatos):**
    - Ligar para múltiplos números (0800 726 0207, 158, 111, SAC 0800 726 0101) até encontrar alguém que dê uma resposta diferente/melhor;
    - Ir presencialmente à agência mesmo quando o problema "deveria" ser resolvido remotamente, na esperança de que o atendimento humano tenha mais autonomia;
    - Registrar reclamações em plataformas públicas (Reclame Aqui) como forma de "furar a fila" e obter resposta institucional mais rápida do que pelo 0800;
    - Tentar sacar via "boca do caixa"/lotérica mesmo com o sistema indicando bloqueio, por orientação informal de um atendente.
11. **Acessibilidade:** existe um canal dedicado (0800 726 2492) para pessoas com deficiência auditiva/de fala, mas não há evidência pública sobre sua integração com o fluxo específico do Seguro-Desemprego, nem sobre opções de Libras em vídeo-atendimento (hipótese de lacuna).

---

## 8. Pontos Ambíguos, Hipóteses e Lacunas (declaração explícita)

1. **Árvore de menus da URA (0800 726 0207):** não foi possível confirmar a estrutura exata de opções (ex.: "digite 1 para Seguro-Desemprego, 2 para FGTS..."), nem se há reconhecimento de voz/fala natural, nem o ponto exato em que a autenticação por CPF/NIS/senha ocorre. **Recomenda-se mapeamento por ligação real (mystery call / shadowing).**
2. **Tempo médio de espera e taxa de abandono de chamadas:** não há dados públicos sobre TME (tempo médio de espera), nível de serviço (% atendido em X segundos) ou taxa de quedas — apenas relatos qualitativos de que "as ligações caem".
3. **Se a URA acessa diretamente a base de habilitação do MTE em tempo real ou uma cópia/réplica com defasagem:** as divergências relatadas sugerem defasagem, mas não há confirmação técnica do mecanismo (batch noturno? réplica assíncrona? webservice síncrono?).
4. **Mecanismo exato de "pagamentos a mais" durante a janela de 5–15 dias de suspensão por novo vínculo:** não está claro se há cobrança/compensação posterior, desconto em parcelas futuras, ou se simplesmente não há reconciliação (potencial fail point adicional não confirmado).
5. **Prazo de requerimento — divergência entre fontes (90 vs. 120 dias para trabalhador formal):** a maioria das fontes (incluindo a página oficial da Caixa indiretamente, via remissão a normas do MTE) aponta 120 dias; uma fonte recente (2026) indica 90 dias "(não 120)". **Necessita validação na fonte primária (MTE/CODEFAT) antes de ser usada no blueprint.**
6. **Formulação exata da carência para 3ª solicitação em diante:** "6 meses de trabalho antes da demissão" vs. "6 meses nos últimos 6 meses" não são necessariamente equivalentes — a segunda formulação implicaria trabalho contínuo nos últimos 6 meses, sem lacunas. **Necessita validação na norma primária.**
7. **Variações regionais de atendimento:** não há indícios de que a URA da Caixa varie por região (parece ser um serviço nacional único), mas o conteúdo do benefício em si pode variar por resoluções regionais pontuais (ex.: MG/2026) — não está claro como (ou se) essas variações são comunicadas pela URA.
8. **Existência de gravação de chamadas, pesquisa de satisfação pós-atendimento, ou SMS/notificações proativas:** não há evidência pública sobre esses elementos para este fluxo específico — apenas inferência por analogia com outros call centers de grande porte.
9. **Operação do 0800 726 0207 — equipe própria Caixa vs. terceirizada:** não foi possível confirmar se o atendimento humano é operado por equipe própria da Caixa ou por empresa terceirizada de telesserviços (comum no setor bancário brasileiro) — relevante para entender autonomia, treinamento e KPIs dos atendentes (backstage).
10. **Integração entre o canal Reclame Aqui (recentemente assumido oficialmente pela Caixa) e o fluxo de atendimento telefônico:** não está claro se uma reclamação aberta no Reclame Aqui gera um protocolo único, rastreável também por telefone, ou se são sistemas isolados.
11. **Volume relativo de chamadas sobre Seguro-Desemprego vs. outros assuntos no mesmo 0800:** a Caixa divulgou estimativa de 250 mil ligações/dia no lançamento do canal (dado antigo, ~2012), sem segmentação por assunto — não se sabe que fração corresponde hoje a Seguro-Desemprego.
12. **Critérios e processo de escalonamento interno (quando um atendente humano não resolve):** não há descrição pública do que acontece "depois" — para qual fila/área um caso de "crédito bloqueado sem explicação" é encaminhado, e qual o SLA esperado.

---

## 9. Síntese — Mapeamento para as 5 Camadas do Blueprint (Jornada B: Consulta de status, fluxo mais frequente)

| Etapa da jornada | Evidências Físicas | Ações do Cidadão | Frontstage | Backstage | Processos de Suporte |
|---|---|---|---|---|---|
| **1. Decisão de ligar** | Divulgação do número 0800 726 0207 (sites, apps, agências) | Cidadão busca/lembra do número | — | — | Material institucional de divulgação |
| **2. Discagem e navegação no menu** | Locução da URA (menu multiassunto: PIS, Seguro-Desemprego, FGTS, Cartão Social, SIC) | Escuta opções, escolhe a relacionada a Seguro-Desemprego (hipótese sobre clareza, ver Seção 8) | URA (sistema automatizado) | — | Plataforma de telefonia/IVR da Caixa |
| **3. Autenticação** | Solicitação de CPF/NIS e Senha Cidadão | Informa dados; pode falhar se não tem senha cadastrada | URA | Base de cadastro de Senha Cidadão | Sistema de autenticação Caixa, vinculado a cadastro feito via lotérica |
| **4. Consulta de status (eletrônica)** | Resposta de voz com status/data/valor | Ouve a resposta; pode ficar com dúvida se diverge do app | URA | Consulta a base/réplica de habilitação (origem MTE) via SISGR | SISGR (sisgr.caixa.gov.br), integração Caixa–MTE |
| **5a. Caminho "resolvido"** | Confirmação verbal da informação | Cidadão encerra a ligação satisfeito | URA | — | — |
| **5b. Caminho "fila para humano"** | Tom de espera (hold) | Aguarda; risco de queda de chamada | Atendente humano Caixa Cidadão (se dentro do horário) | Sistema de filas/CRM do call center | Infraestrutura de telefonia, possivelmente terceirizada (não confirmado) |
| **6. Atendente humano consulta divergência** | Atendente relata o que vê no sistema | Cidadão expõe a divergência (ex.: "app diz bloqueado, mas...") | Atendente Caixa | Mesma base SISGR/MTE; possível abertura de chamado interno | Sistema de tickets/CRM (não confirmado) |
| **7. Sem resolução imediata → orientação** | Protocolo de atendimento (se gerado); orientação verbal | Cidadão recebe instrução genérica ("aguarde", "procure agência") | Atendente Caixa | Encaminhamento a área responsável (Caixa) ou indicação de que é assunto do MTE | Fluxo de escalonamento (estrutura não confirmada) |
| **8. Cidadão busca canal alternativo** | App Carteira de Trabalho Digital / 158 / Reclame Aqui / agência física | Cidadão repete a consulta em outro canal | Central 158 (MTE) / Atendente de agência / Reclame Aqui | Sistema de habilitação MTE (fonte primária dos dados) | Portal Emprega Brasil, Ouvidoria MTE |
| **9. Resolução eventual** | Crédito efetivado + comprovante/extrato | Cidadão confirma recebimento | Caixa (rede de pagamento) | Processamento de pagamento/lote (Agente Pagador) | FAT, sistemas de liquidação bancária |

---

## Fontes consultadas (síntese)

- Páginas institucionais da Caixa Econômica Federal: seção "Benefícios do Trabalhador – Seguro-Desemprego" (incluindo FAQ) e seção "Atendimento" (canais e telefones).
- Reportagens sobre o lançamento e funcionamento do canal "Atendimento Caixa ao Cidadão" (0800 726 0207).
- Portal Emprega Brasil / serviços do MTE (servicos.mte.gov.br).
- IBGE — Comitê de Estatísticas Sociais, metadados sobre o processo de habilitação do Seguro-Desemprego (pré-triagem, triagem, habilitação).
- Conteúdos de terceiros (blogs especializados em benefícios e direito do trabalho) sobre valores, carência, prazos e tabela de parcelas para 2025/2026 — usados com cautela e marcados como pontos a validar quando divergentes.
- Reclamações públicas de cidadãos na plataforma Reclame Aqui sobre bloqueios de crédito, atrasos de parcelas e atendimento, incluindo respostas institucionais da Caixa.
- Legislação e resoluções citadas: Lei nº 7.998/1990; Lei nº 14.075/2020; Resolução CODEFAT nº 957/2022; Resolução CODEFAT/MTE nº 1.036/2026.

---

## Recomendações para validação adicional (próximos passos sugeridos)

1. Realizar ligações de teste (shadowing) para o 0800 726 0207 em diferentes horários (pico e fora de pico, dias úteis e sábado) para mapear a árvore de menus real, tempos de espera e taxa de queda.
2. Validar, em fonte primária do MTE/CODEFAT, os prazos de requerimento (90 vs. 120 dias) e a formulação exata da carência para a 3ª solicitação em diante.
3. Entrevistar cidadãos que passaram recentemente pelo processo (entrada, consulta, renovação) para validar as jornadas A–D e identificar gambiarras adicionais.
4. Confirmar com a Caixa (ou via LAI — Lei de Acesso à Informação) se o atendimento telefônico é operado internamente ou por terceirizada, e quais SLAs internos existem para escalonamento.
5. Verificar se há, de fato, sincronização defasada entre os sistemas Caixa e MTE, e qual a frequência/mecanismo dessa sincronização — essencial para entender a causa raiz da maioria dos fail points de status divergente.
