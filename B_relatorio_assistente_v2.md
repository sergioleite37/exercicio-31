# Pesquisa AS-IS v2 — Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal
## (Revisão pós-auditoria — resposta falha a falha)

## Nota de versão

Esta v2 revisa a pesquisa original (v1) à luz da auditoria recebida ("B_relatorio_auditoria_v1.pdf"), que apontou 5 falhas categorizadas. Cada falha foi tratada com uma ação explícita — **(a) Corrigir**, **(b) Defender** ou **(c) Marcar como pendente** — e, quando a correção exigiu, foi feita pesquisa adicional em fontes primárias (textos de lei e resoluções do CODEFAT na íntegra, não apenas em conteúdos de terceiros). A estrutura geral da v1 (8 tópicos + síntese para as 5 camadas do blueprint) é mantida; esta v2 está organizada em três partes:

- **Parte I** — registro de auditoria, falha a falha, com rastreabilidade explícita.
- **Parte II** — pesquisa revisada, já incorporando as correções, organizada conforme as camadas do Service Blueprint solicitadas (Jornada, Evidências Físicas, Frontstage, Backstage, Processos de Suporte, Normativos, Fail Points, Ambiguidades).
- **Parte III** — síntese atualizada de mapeamento para as 5 camadas.

Onde uma seção da v1 **não foi afetada** por nenhuma falha da auditoria, isso é declarado explicitamente, em vez de repetir o conteúdo na íntegra — para manter a rastreabilidade clara entre v1 → auditoria → v2.

---

# Parte I — Resposta à Auditoria, Falha a Falha

## Tabela-síntese de rastreabilidade

| # | Categoria (auditoria) | Trecho/tema original | Ação | Onde tratado na v2 |
|---|---|---|---|---|
| 1 | Erro factual | Tabela "1 parcela: 30–44 dias ... 5 parcelas: 135–164 dias" atribuída de forma genérica ao Seguro-Desemprego | (a) Corrigir | Parte II, Seção 6 (Normativos) |
| 2 | Backstage omitido | Ausência da etapa de retorno/rejeição de crédito bancário | (a) Corrigir/Complementar | Parte II, Seções 4 e 7 |
| 3a | Normativo ausente — LGPD | Ausência de referência à Lei nº 13.709/2018 sobre dados na URA | (a) Corrigir, com sub-ponto (c) pendente | Parte II, Seções 2, 5 e 6; Seção 8 (item novo) |
| 3b | Normativo ausente — Convênio MTE-Caixa | Ausência de referência ao instrumento que rege o SLA Caixa-MTE | (c) Marcar como pendente | Parte II, Seções 5 e 8 (item novo) |
| 4 | Fail point não identificado | Bloqueio de Senha Cidadão por tentativas (DTMF/"fat finger") | (a) Corrigir/Adicionar, com sub-ponto (c) pendente | Parte II, Seções 1, 7 e 8 |
| 5 | Inferência mal suportada | "URA não avalia carência por ser sistema de áudio pré-gravado" | (a) Corrigir framing + (b) Defender conclusão por razão distinta | Parte II, Seção 1 (Jornada C) e Seção 7 |

---

## Falha 1 — Erro factual: tabela de parcelas por dias (30–164 dias)

**Identificação:** Categoria "Erros factuais". Trecho original (Seção 6 da v1): a tabela "1 parcela, se o período for de 30 a 44 dias [...] 5 parcelas, se o período for de 135 a 164 dias", apresentada como regra geral de definição do número de parcelas do Seguro-Desemprego, com base na Resolução CODEFAT nº 957/2022.

**Ação escolhida:** **(a) Corrigir**, com uma ressalva importante sobre a origem da informação (ver Justificativa).

**Justificativa:** A auditoria está **parcialmente correta, mas a causa raiz do erro foi mal diagnosticada**. Pesquisa adicional em fontes primárias confirma dois pontos:

1. **A tabela "30–164 dias / 1–5 parcelas" existe de fato na Resolução CODEFAT nº 957/2022** — não é uma invenção nem um erro de citação de norma. Ela **não se aplica, porém, ao trabalhador formal dispensado sem justa causa** (o público majoritário do serviço investigado), e sim à **Bolsa de Qualificação Profissional** (art. 2º-A da Lei nº 7.998/1990 — benefício pago ao trabalhador com contrato suspenso para participar de curso/programa de qualificação oferecido pelo empregador). A v1 citou a norma corretamente, mas **aplicou a regra à modalidade errada do benefício** — um erro de enquadramento, não de invenção de fonte.
2. **Para o trabalhador formal e o trabalhador doméstico** (situação típica de quem liga para a URA por ter sido demitido sem justa causa), a regra correta — confirmada no texto da **Lei nº 7.998/1990, art. 4º, §2º, na redação dada pela Lei nº 8.900/1994**, e mantida pela Resolução CODEFAT nº 957/2022 — é baseada no **tempo de vínculo empregatício nos 36 meses que antecederam a dispensa**:
   - **3 parcelas**: de 6 a 11 meses trabalhados nos últimos 36 meses;
   - **4 parcelas**: de 12 a 23 meses trabalhados nos últimos 36 meses;
   - **5 parcelas**: 24 meses ou mais trabalhados nos últimos 36 meses.
   - **O mínimo é sempre 3 parcelas** — a auditoria está correta neste ponto: não existe hipótese de 1 ou 2 parcelas para o trabalhador formal/doméstico dispensado sem justa causa.

A informação corretiva da auditoria ("mínimo 3 parcelas, podendo chegar a 4 ou 5") está **alinhada com fontes oficiais** (ex.: conteúdo do MTE replicado por terceiros confirma "o trabalhador tem direito a receber de 3 a 5 parcelas do seguro-desemprego, a depender do tempo trabalhado"). A v1 já indicava "3 a 5 parcelas" em outros trechos (Seção 6, parágrafo sobre valores), o que tornava o documento **internamente inconsistente** — outro motivo para a correção.

**Texto revisado (substitui o trecho da Seção 6 da v1):**

> O **número de parcelas do Seguro-Desemprego varia conforme a modalidade do benefício**, e a v1 misturou duas regras distintas:
>
> **(A) Trabalhador formal e trabalhador doméstico (dispensa sem justa causa) — regra aplicável à maioria das ligações para a URA:**
> Definido pelo **tempo de vínculo empregatício nos 36 meses anteriores à dispensa** (Lei nº 7.998/1990, art. 4º, §2º, com redação da Lei nº 8.900/1994; mantido pela Resolução CODEFAT nº 957/2022):
> - 6 a 11 meses trabalhados → **3 parcelas**
> - 12 a 23 meses trabalhados → **4 parcelas**
> - 24 a 36 meses trabalhados → **5 parcelas**
> - **Nunca há concessão de 1 ou 2 parcelas nesta modalidade.**
>
> **(B) Bolsa de Qualificação Profissional (contrato suspenso para curso/qualificação oferecido pelo empregador) — modalidade distinta, regida pelo art. 2º-A da Lei nº 7.998/1990 e pela Resolução CODEFAT nº 957/2022:**
> Aqui sim existe uma tabela baseada em **dias** de "período de desemprego"/suspensão:
> - 30 a 44 dias → 1 parcela
> - 45 a 74 dias → 2 parcelas
> - 75 a 104 dias → 3 parcelas
> - 105 a 134 dias → 4 parcelas
> - 135 a 164 dias → 5 parcelas
>
> **Implicação para o Service Blueprint:** se a URA atender também ligações de trabalhadores em Bolsa de Qualificação Profissional (público minoritário, mas existente), ela precisa diferenciar a modalidade **antes** de informar o número de parcelas — caso contrário, há risco real de informar a um trabalhador formal dispensado que ele "só tem direito a 1 ou 2 parcelas", o que estaria errado e geraria uma reclamação/escalonamento evitável. Esse é, portanto, **um fail point potencial adicional**, tratado na Seção 7.

---

## Falha 2 — Backstage omitido: retorno/rejeição de crédito bancário

**Identificação:** Categoria "Etapas de backstage omitidas". Trecho original (Seção 4, item 4, da v1): descrição do "Processamento de pagamento (Caixa, como Agente Pagador)" sem menção ao fluxo de devolução/rejeição quando a transferência para outra instituição falha.

**Ação escolhida:** **(a) Corrigir/Complementar.**

**Justificativa:** A auditoria está correta em apontar uma lacuna real, e há **base normativa direta** que sustenta a existência de um fluxo de devolução: a **Resolução CODEFAT nº 957/2022 estabelece que a parcela fica disponível para saque por 67 dias**, após os quais **deve ser devolvida pelo agente pagador (Caixa) ao FAT**. Isso confirma que existe, sim, um processo de backstage de **conciliação/devolução de valores não sacados ou não creditados** — exatamente o tipo de etapa que a v1 não mencionou.

Dito isso, **uma ressalva de rigor**: a auditoria nomeia esse processo especificamente como "gerido pela Câmara Interbancária de Pagamentos (SPB/PIX)" e usa o rótulo "recurso devolvido". Não encontrei, nas fontes consultadas, uma referência específica do Seguro-Desemprego a esse rótulo exato ou a essa câmara especificamente (PIX é usado para outras finalidades na Caixa, mas não há confirmação de que o crédito do Seguro-Desemprego para "qualquer instituição financeira informada pelo trabalhador" seja necessariamente via PIX vs. TED vs. crédito em conta corrente tradicional). Portanto, **incorporo a etapa como backstage real e relevante (corrigir)**, mas **marco a nomenclatura/mecanismo bancário exato como pendente** (ver Seção 8, novo item).

**Texto revisado (complementa a Seção 4 da v1, novo item 4-bis):**

> **4-bis. Conciliação de retorno/rejeição de crédito (Caixa, Agente Pagador):** quando o crédito da parcela não pode ser efetivado na conta informada pelo trabalhador (conta encerrada, dados bancários incorretos, divergência de titularidade, ou indisponibilidade técnica do sistema de transferência — como no incidente sistêmico de junho/2025 mencionado na v1), o valor **retorna à Caixa** e precisa ser reconciliado. A Resolução CODEFAT nº 957/2022 estabelece uma janela de **67 dias de disponibilidade para saque**, após a qual o valor não sacado deve ser **devolvido ao FAT** pelo agente pagador. Isso implica:
> - Uma fila/processo interno de "pagamentos pendentes de reconciliação", que provavelmente não é visível em nenhum app do cidadão (status "emitida"/"bloqueado" não diferencia "aguardando primeira tentativa" de "retornado e em reprocessamento");
> - Um prazo (67 dias) após o qual, se o cidadão não regularizar seus dados bancários e sacar o valor, o dinheiro **sai do circuito do benefício e volta ao FAT** — criando uma janela de risco para o cidadão que demora a perceber o bloqueio;
> - Esta etapa é adicionada também como **novo fail point (#13)** na Seção 7.

---

## Falha 3 — Normativos ausentes: LGPD e Convênio/Contrato MTE-Caixa

A auditoria trata os dois normativos no mesmo ponto, mas eles têm naturezas muito diferentes — por isso a resposta é dividida em 3a (LGPD) e 3b (Convênio MTE-Caixa).

### Falha 3a — Lei Geral de Proteção de Dados (Lei nº 13.709/2018)

**Identificação:** ausência de referência à LGPD como normativo que regula o tratamento de CPF, NIS, dados financeiros e senha na URA.

**Ação escolhida:** **(a) Corrigir** (incluir a LGPD como normativo relevante, em termos gerais), **com um sub-ponto (c) marcado como pendente** (a alegação específica sobre regras de TTS).

**Justificativa:** A auditoria está correta em que a LGPD é **um normativo relevante e estava ausente** — qualquer canal que colete CPF, NIS e autentique por senha numérica para fornecer dados financeiros está sujeito à LGPD, inclusive quando o agente de tratamento (Caixa) atua em nome de outro controlador (MTE/FAT). Isso é incorporado.

Porém, a auditoria vai além e afirma que a LGPD **"baliza os limites de autenticação e define exatamente que tipo de dados sensíveis ou financeiros a URA pode verbalizar autonomamente (Text-to-Speech) antes de exigir validação humana ou presencial"**. Essa afirmação é **mais específica do que o que a LGPD, como lei geral, efetivamente dispõe** — a LGPD estabelece princípios (finalidade, adequação, necessidade, segurança, minimização) e bases legais de tratamento, mas **não contém uma lista operacional de "o que uma URA pode falar em voz alta"**. Esse tipo de regra, se existir, estaria em **normas internas de segurança da informação** (Caixa/MTE) ou em regulamentação setorial (ex.: normas do Banco Central sobre canais remotos), não diretamente no texto da LGPD. Por isso, mantenho a inclusão da LGPD como normativo aplicável (corrigir), mas marco como **pendente** a existência de uma norma específica e pública que regule o roteiro de TTS da URA.

**Texto revisado (novo item na Seção 6 — Normativos):**

> **Lei nº 13.709/2018 (Lei Geral de Proteção de Dados — LGPD):** aplica-se a todo o fluxo de atendimento da URA, na medida em que há coleta e tratamento de CPF, NIS/PIS, e validação por Senha Cidadão para acesso a dados financeiros (situação do benefício, valores, datas de crédito). Princípios diretamente relevantes:
> - **Finalidade e adequação** (art. 6º, I e II): os dados coletados na URA devem se limitar ao necessário para a autenticação e a consulta solicitada;
> - **Segurança e prevenção** (art. 6º, VII e VIII; art. 46): a Caixa, como operadora/agente de tratamento atuando sobre uma base cuja titularidade da informação de habilitação é do MTE, deve adotar medidas técnicas para evitar acessos não autorizados — o que dá um fundamento legal adicional (além da experiência do usuário) para a exigência de Senha Cidadão antes de informações financeiras detalhadas;
> - **Possível base legal**: tratamento para cumprimento de obrigação legal/execução de política pública (art. 7º, II e III), dado que o Seguro-Desemprego é benefício previsto em lei e operado por entidade pública/órgão.
>
> **Pendência explícita:** não há, nas fontes públicas consultadas, um normativo específico (interno ou setorial) que detalhe **quais dados a URA pode verbalizar de forma autônoma via TTS** antes de exigir autenticação completa, validação humana, ou comparecimento presencial. Recomenda-se buscar essa informação em normas internas de segurança da informação da Caixa/MTE (não públicas) — ver Seção 8.

### Falha 3b — Convênio/Contrato de Prestação de Serviços MTE-Caixa

**Identificação:** ausência de referência ao instrumento jurídico que define as obrigações e SLAs da Caixa como operadora do canal de atendimento sobre um benefício gerido pelo MTE.

**Ação escolhida:** **(c) Marcar como pendente.**

**Justificativa:** A existência de **algum instrumento formal** (convênio, termo de cooperação, ou ato regulamentar do CODEFAT que designa a Caixa como Agente Pagador) é **altamente provável** — a própria Lei nº 7.998/1990 (art. 19) atribui ao CODEFAT a competência para disciplinar a atuação do agente pagador, e a Resolução CODEFAT nº 957/2022 trata extensamente das obrigações do "agente pagador". No entanto, **não localizei, nas fontes públicas consultadas, o texto integral ou o número específico de um "Convênio/Contrato Caixa-MTE" com SLAs detalhados de atendimento** (tempos de resposta, taxas de queda aceitáveis, obrigações de comunicação ao cidadão, etc.). Diferente da Falha 3a (onde a LGPD é claramente identificável como lei aplicável, ainda que sem detalhamento operacional público), aqui **nem a existência do documento específico, nem seu conteúdo, podem ser confirmados** com as fontes disponíveis — por isso a ação é marcar como pendente, e não corrigir.

**Descrição da ambiguidade e o que resolveria:**

> Existe, com alta probabilidade, um instrumento (convênio, contrato, ou disciplina via resolução CODEFAT) que rege a relação Caixa–FAT/MTE como Agente Pagador do Seguro-Desemprego, incluindo possivelmente obrigações de atendimento ao cidadão. **Para validar:**
> - Buscar, via Lei de Acesso à Informação (LAI), o instrumento jurídico vigente entre a Caixa e o FAT/MTE para a função de Agente Pagador do Seguro-Desemprego;
> - Verificar na Resolução CODEFAT nº 957/2022 (texto integral, artigos sobre "agente pagador") se há cláusulas de SLA de atendimento ao cidadão, ou se o instrumento de SLA é separado da resolução;
> - Sem esse documento, **não é possível** afirmar quais compromissos de tempo de resposta, taxa de resolução, ou comunicação proativa a Caixa assumiu — o que limita a análise de "gaps de SLA" no blueprint (ex.: não dá para dizer se uma fila de 20 minutos está "dentro" ou "fora" do acordado).

---

## Falha 4 — Fail point não identificado: bloqueio de Senha Cidadão por tentativas (DTMF)

**Identificação:** Categoria "Fail points não identificados". Trecho original (Seção 1.2, item 4, da v1): aborda apenas o cenário de "cidadão nunca cadastrou a Senha Cidadão", sem cobrir o cenário de bloqueio por tentativas incorretas durante uma ligação.

**Ação escolhida:** **(a) Corrigir/Adicionar** o fail point, **com um sub-ponto (c) marcado como pendente** sobre o caminho de resolução.

**Justificativa:** O fail point apontado pela auditoria é **plausível e tecnicamente bem fundamentado** — sistemas de autenticação por PIN numérico (DTMF) com bloqueio antifraude após N tentativas incorretas são um padrão amplamente conhecido em centrais telefônicas bancárias, e a Senha Cidadão (6 dígitos) é exatamente esse tipo de credencial. É um fail point **diferente** do já descrito na v1 ("não possui senha cadastrada") — este é "**possui senha, mas a digitou errado repetidas vezes e agora está bloqueado**", o que é incorporado como novo item.

Entretanto, há uma **ressalva importante que a própria v1 já continha** (Seção "Fontes", documento sobre cadastro de Senha Cidadão): existe um trecho (truncado na pesquisa original) que sugere que "**o desbloqueio também pode ser feito pelos mesmos canais**" — ou seja, telefone ou internet, e não necessariamente exigindo presença física. A auditoria afirma categoricamente que esse fail point "**força obrigatoriamente o utente a deslocar-se a uma agência física ou lotérica**" — essa afirmação **pode estar correta para bloqueios por segurança/fraude em geral**, mas **não há confirmação específica de que o bloqueio por excesso de tentativas na URA siga exatamente essa regra** (poderia, em tese, ser desbloqueado remotamente após confirmação de identidade por outros meios). Por isso, **incorporo o fail point (corrigir/adicionar)**, mas **marco como pendente a forma exata de resolução** (remota vs. presencial obrigatória).

**Texto revisado (novo fail point, detalhado na Seção 7, item #12):**

> **Bloqueio de Senha Cidadão por excesso de tentativas incorretas (erro de digitação no teclado — "fat finger"):** durante a autenticação na URA (digitação de CPF/NIS + Senha Cidadão de 6 dígitos via teclado numérico do telefone), erros de digitação repetidos podem acionar bloqueio automático por suspeita de fraude. Diferente do cenário "nunca cadastrei senha" (já descrito na v1), aqui o cidadão **tinha** uma senha válida e a perdeu por bloqueio operacional. Esse é um ponto de ruptura **dentro da própria ligação** — o cidadão que estava tentando se autenticar para uma consulta de rotina pode sair da ligação em pior situação do que entrou (sem acesso a nenhum canal de autoatendimento até desbloquear a senha).
>
> **Pendência:** não está confirmado se o desbloqueio por excesso de tentativas (i) pode ser feito remotamente, por telefone/internet, mediante validação alternativa de identidade, ou (ii) exige obrigatoriamente comparecimento presencial (agência/lotérica), como ocorre — segundo fontes da v1 — no cadastro inicial da senha. Essa distinção muda significativamente a severidade do fail point no blueprint (ruptura temporária vs. ruptura que força um canal físico).

---

## Falha 5 — Inferência mal suportada: "URA não avalia carência por ser sistema de áudio pré-gravado"

**Identificação:** Categoria "Inferências mal suportadas ou fontes fracas". Trecho original (Seção 1.3, item 2, da v1): "A URA, sendo um sistema de respostas pré-gravadas/genéricas, provavelmente não tem capacidade de avaliar a carência individual do cidadão — ela pode, no máximo, informar a regra geral."

**Ação escolhida:** **(a) Corrigir o enquadramento/framing da inferência** + **(b) Defender a conclusão prática para a Jornada C, por uma razão diferente da originalmente apresentada.**

**Justificativa:**

A auditoria está **correta ao apontar que a v1 errou a causa**: URAs modernas operam com **integração via API a sistemas de backend e Text-to-Speech (TTS) com variáveis dinâmicas** — ou seja, o fato de a interface ser "de voz"/"pré-gravada" **não impede**, por si só, que o sistema verbalize um resultado específico e individualizado (ex.: "sua próxima parcela de R$ 1.621,00 está prevista para 15/07"), **desde que esse resultado já exista em algum sistema de backend e o cidadão esteja autenticado**. A própria v1 já demonstrava isso na Jornada B, item 5 ("se autenticado, o sistema informa dados como situação do benefício, data prevista de crédito, valor da parcela") — havia, portanto, **uma contradição interna** entre essa parte (que assume capacidade de informação individualizada) e a inferência da Jornada C (que assume incapacidade). A auditoria identificou corretamente essa inconsistência. **Corrijo o framing**: a limitação não é "porque a URA é um sistema de áudio".

Porém, **defendo que a conclusão prática para a Jornada C permanece majoritariamente válida — por um motivo estrutural diferente, não tecnológico**: na Jornada C (cidadão quer **requerer novamente** o benefício, ainda não há um novo requerimento em processamento), **não existe, no momento da ligação, um resultado de habilitação a ser consultado** — a avaliação de carência para uma *nova* solicitação só é processada **depois** que o requerimento é formalmente submetido (etapas de pré-triagem/triagem descritas na Seção 4 da v1, baseadas na documentação do IBGE/MTE). Ou seja:

- Para a Jornada B (consultar um benefício **já requerido/habilitado**): a URA, com integração de API e TTS, **tem sim capacidade técnica de informar dados individualizados** — a auditoria está certa, e a v1 já refletia isso (com a inconsistência apontada).
- Para a Jornada C (avaliar **se um cidadão teria direito**, antes de submeter um novo requerimento): **não há, estruturalmente, um "resultado" para a URA buscar e verbalizar** — a avaliação de carência (incluindo a regra específica "cada um dos 6 meses imediatamente anteriores", confirmada na Seção 6 revisada) **é parte do processamento do requerimento em si**, feito pelo sistema de habilitação do MTE no momento em que o pedido é submetido, não antes. Portanto, mesmo uma URA tecnicamente "moderna" **não teria uma "carência pré-calculada"** para consultar nesse cenário — a limitação é de **disponibilidade de dado no momento certo do processo**, não de capacidade de voz.

**Texto revisado (substitui o trecho da Seção 1.3, item 2, da v1):**

> **2. Diferença-chave (revisado):** as regras de carência mudam conforme o número de solicitações anteriores (1ª: 12 em 18 meses; 2ª: 9 em 12 meses; 3ª em diante: cada um dos 6 meses imediatamente anteriores à dispensa — ver Seção 6). **Diferentemente do que a v1 afirmava, a limitação da URA aqui não decorre de ela ser um "sistema de áudio pré-gravado"** — URAs modernas integram-se via API a sistemas de backend e usam TTS com variáveis dinâmicas, sendo plenamente capazes de verbalizar resultados individualizados quando esses resultados existem (como demonstrado na própria Jornada B, para consulta de um benefício já habilitado).
>
> **A limitação real é estrutural/temporal**: a avaliação de carência para uma **nova** solicitação é parte do **processamento do requerimento em si** (etapas de pré-triagem/triagem do MTE), e só existe **depois** que o requerimento é submetido — não antes, como uma "simulação" prévia. Portanto, ainda que a URA pudesse, em tese, consultar qualquer sistema do MTE em tempo real, **não haveria, no momento da ligação, um resultado de habilitação individual a ser consultado** para uma solicitação ainda não feita. A URA pode, no máximo, informar a regra geral de carência (texto fixo) — não porque "é de áudio", mas porque **o dado individualizado correspondente ainda não existe no sistema** nesse ponto da jornada.

---

# Parte II — Pesquisa Revisada (estrutura Service Blueprint AS-IS)

## 1. Jornada do Cidadão

**Status:** Jornadas A, B, C e D da v1 são **mantidas em sua estrutura geral** (não houve falha apontada quanto à sequência básica de etapas). Duas atualizações pontuais foram inseridas, ambas detalhadas na Parte I:

- **Jornada B, novo ponto de ruptura (decorrente da Falha 4):** após o "Ponto de decisão 2 — Cidadão não possui a senha cadastrada" (v1), insere-se um **novo ponto de decisão 2-bis — Cidadão possui senha, mas é bloqueado por tentativas incorretas durante a digitação na URA**. Este ponto de ruptura ocorre *dentro* da ligação (ao contrário do 2, que é uma condição pré-existente) e pode ser mais frequente, já que depende apenas de erro de digitação no teclado do telefone — uma interface historicamente propensa a erro (números pequenos, ausência de feedback visual, nervosismo do cidadão ao lidar com um assunto financeiro sensível).
- **Jornada B/D, novo ramo de backstage (decorrente da Falha 2):** quando a "Discrepância entre canais" (item 6 da Jornada B na v1) tem como causa raiz um **retorno/rejeição de crédito bancário não reconciliado**, a jornada do cidadão pode se prolongar por até **67 dias** (prazo de disponibilização da Resolução CODEFAT 957/2022) antes que o valor seja efetivamente devolvido ao FAT — um prazo que, do ponto de vista do cidadão, é indistinguível de "está tudo bem, só demorando" até que se torne "perdi o direito a essa parcela porque não regularizei a tempo".
- **Jornada C, item 2 revisado (decorrente da Falha 5):** ver texto revisado na Parte I — a explicação de por que a URA não pode antecipar o resultado de carência para uma nova solicitação foi reescrita com base estrutural/temporal, não tecnológica.

Todos os demais elementos das Jornadas A, B, C e D (gatilhos, bifurcações de canal Caixa↔MTE, escalonamentos, "loop" para quem não tem app/conta Gov.br) permanecem válidos e não foram contestados pela auditoria.

---

## 2. Evidências Físicas e Perceptíveis em Cada Etapa

**Status:** a tabela de evidências da v1 é majoritariamente mantida. Duas adições:

| Evidência (nova/revisada) | Onde aparece | Qualidade/Clareza observada |
|---|---|---|
| **Mensagem de bloqueio de Senha Cidadão por tentativas** (novo — Falha 4) | Durante autenticação na URA, após N tentativas incorretas | Não há confirmação do texto exato dessa mensagem nem se ela informa o caminho de desbloqueio (presencial vs. remoto) — provável fonte de frustração imediata |
| **Aviso de prazo de 67 dias para saque / devolução ao FAT** (novo — Falha 2) | Em tese, deveria constar no calendário de pagamento (Portal Emprega Brasil/app) | Não há confirmação de que esse prazo seja comunicado de forma proativa e destacada ao cidadão — risco de o cidadão "perder" o prazo sem perceber |
| **Coleta de CPF/NIS/Senha na URA — sob a ótica da LGPD** (revisão normativa — Falha 3a) | Etapa de autenticação | A v1 descrevia a coleta, mas sem associá-la ao arcabouço da LGPD (Lei nº 13.709/2018) como referência normativa para a qualidade/segurança dessa evidência — ver Seção 6 |

As demais evidências (Requerimento do Seguro-Desemprego, locução/menu da URA, status divergentes entre apps, protocolo de reclamação, comprovante de saque, calendário de pagamento) **mantêm-se como descritas na v1**, sem contestação na auditoria.

---

## 3. Frontstage (Atores Visíveis ao Cidadão)

**Status:** **sem alterações em relação à v1** — nenhuma falha da auditoria questionou a lista ou a caracterização dos atores de frontstage (URA, atendente humano Caixa Cidadão, central 158/MTE, apps/chat, canal PcD 0800 726 2492, atendente de agência, casa lotérica, posto SINE/SRTE). Vale apenas registrar que o **atendente de agência/lotérica** é agora também o ator relevante para o desbloqueio de Senha Cidadão (Falha 4), reforçando seu papel de "canal de última instância" já descrito na v1.

---

## 4. Backstage (Atores e Processos Fora da Visibilidade do Cidadão)

**Status:** lista da v1 mantida (itens 1 a 9), com **um novo item** decorrente da Falha 2:

> **4-bis. Conciliação de retorno/rejeição de crédito e devolução ao FAT (Caixa, Agente Pagador):** quando o crédito de uma parcela não é efetivado na conta indicada (conta encerrada, dados incorretos, divergência de titularidade, ou falha sistêmica de transferência — como o incidente de junho/2025 já citado na v1), o valor retorna à Caixa e entra em um processo de reconciliação. A **Resolução CODEFAT nº 957/2022** define que o valor disponibilizado para saque que não for sacado em **67 dias** deve ser **devolvido pelo Agente Pagador ao FAT**. Este processo:
> - Provavelmente gera um status interno (não confirmado se visível ao cidadão) distinto de "emitida" e de "crédito bloqueado" — algo como "retornado/pendente de reprocessamento";
> - Cria uma **janela de tempo finita (67 dias)** dentro da qual o cidadão precisa agir (atualizar dados bancários, comparecer a um canal de saque) para não perder o valor da parcela;
> - Conecta-se ao item 5 da v1 (Equipe de incidentes/operações de transferência) — um incidente sistêmico de transferência (ex.: junho/2025) provavelmente **alimenta este mesmo processo de conciliação em volume anormalmente alto**, o que pode explicar por que a comunicação ao cidadão, nesses casos, chega depois e por canais diferentes (Reclame Aqui) do status do app.

Os demais itens do backstage (pré-triagem, triagem automatizada via eSocial/CAGED/RAIS, habilitação, processamento de pagamento em lote, auditoria/suspensão automática por novo vínculo, gestão de reclamações/Ouvidoria, gestão de exceções normativas regionais, fluxo de informação Caixa↔MTE) **mantêm-se como na v1**, sem contestação direta da auditoria — embora a Falha 5 reforce, especificamente para o item "Habilitação (MTE)", que essa etapa é o **único lugar onde a avaliação de carência de uma nova solicitação acontece** (não há "pré-avaliação" disponível para consulta antes da submissão).

---

## 5. Processos de Suporte (Infraestrutura Técnica e Operacional)

**Status:** tabela da v1 mantida, com **três adições**:

| Sistema/Infraestrutura (novo/revisado) | Função aparente | Operador |
|---|---|---|
| **Sistema antifraude de bloqueio de Senha Cidadão por tentativas** (novo — Falha 4) | Bloqueia credenciais após N tentativas incorretas de PIN em canais de autoatendimento (URA, apps, sites) | Caixa — mecanismo e canal de desbloqueio não confirmados (pendente) |
| **Processo de conciliação/devolução ao FAT (67 dias)** (novo — Falha 2) | Reconcilia créditos não efetivados/não sacados e devolve ao FAT após o prazo regulamentar | Caixa (Agente Pagador), com destino FAT/CODEFAT |
| **Arcabouço LGPD (Lei nº 13.709/2018)** (novo — Falha 3a) | Regula princípios de tratamento de dados pessoais (CPF, NIS, dados financeiros) coletados/consultados via URA | Aplicável a Caixa e MTE como agentes de tratamento; detalhamento operacional (regras de TTS) não confirmado |
| **Instrumento Caixa–FAT/MTE (Agente Pagador) — SLAs de atendimento** (novo — Falha 3b) | Presumível instrumento que rege obrigações/SLAs da Caixa na operação do canal de atendimento sobre o benefício gerido pelo MTE | **Pendente** — existência presumida (Lei nº 7.998/1990, art. 19 + Resolução CODEFAT 957/2022), conteúdo específico não localizado |

As **limitações técnicas conhecidas** listadas na v1 (falta de visão unificada Caixa-MTE, latência de 5–15 dias na suspensão, dependência de canais físicos, falhas sistêmicas em lote, dependências externas eSocial/CAGED/RAIS/Receita) **permanecem válidas e são reforçadas** pelas novas informações: a "falta de visão unificada" agora também explica, em parte, por que o processo de conciliação/devolução (4-bis) pode não ser visível ao cidadão como um status distinto.

---

## 6. Normativos, Regras e Critérios Relevantes (seção mais revisada)

### 6.1 Base legal geral
- **Lei nº 7.998, de 11 de janeiro de 1990** (com as alterações da **Lei nº 8.900/1994** e, principalmente, da **Lei nº 13.134/2015**, que revisou substancialmente as regras de carência e revogou dispositivos anteriores): institui o Programa do Seguro-Desemprego, o Abono Salarial e o FAT; base da atuação da Caixa como Agente Pagador.
- **Lei nº 14.075/2020**: permite pagamento de benefícios sociais (incl. Seguro-Desemprego) via Conta Poupança Social Digital (app Caixa Tem).
- **Resolução CODEFAT nº 957, de 21 de setembro de 2022** (consolidação das normas de concessão, processamento e pagamento — revoga, entre outras, a Resolução CODEFAT nº 467/2005): regula trabalhador formal, doméstico, pescador artesanal, trabalhador resgatado e Bolsa de Qualificação Profissional em um único ato.
- **Resolução CODEFAT/MTE nº 1.036, de 3 de março de 2026**: exemplo de norma de exceção regional (parcelas adicionais para municípios específicos de MG) — mantido da v1, sem alteração.
- **(Novo — Falha 3a) Lei nº 13.709/2018 (LGPD)**: aplicável ao tratamento de CPF, NIS e dados financeiros no canal de atendimento — ver texto completo na Parte I, Falha 3a.

### 6.2 Carência (tempo mínimo trabalhado) — **revisado com base em fonte primária (Lei nº 7.998/1990, art. 3º, I, na redação da Lei nº 13.134/2015)**

Esta seção resolve diretamente a **Ambiguidade #6 da v1** ("formulação exata da carência para 3ª solicitação em diante"):

- **1ª solicitação**: pelo menos 12 meses trabalhados nos últimos 18 meses imediatamente anteriores à dispensa;
- **2ª solicitação**: pelo menos 9 meses trabalhados nos últimos 12 meses imediatamente anteriores à dispensa;
- **3ª solicitação em diante**: **"cada um dos 6 (seis) meses imediatamente anteriores à data de dispensa"** — ou seja, **trabalho contínuo, sem lacunas, nos 6 meses imediatamente anteriores à dispensa**, e não "qualquer 6 meses de trabalho em algum momento". **A interpretação mais restritiva, levantada como hipótese na v1, é a correta**, segundo a redação literal da lei dada pela Lei nº 13.134/2015.

> **Nota:** a Lei nº 13.134/2015 também revogou o art. 2º-B da Lei nº 7.998/1990 (regra excepcional de 3 parcelas de R$ 100 para desempregados de longa duração entre 12–18 meses) — citado aqui apenas para registro histórico, sem impacto na operação atual.

### 6.3 Número de parcelas — **seção totalmente reescrita (resposta à Falha 1)**

Ver texto completo na Parte I, Falha 1. Em resumo:
- **Trabalhador formal/doméstico (dispensa sem justa causa)**: 3 a 5 parcelas, por **meses trabalhados nos últimos 36 meses** (6–11 = 3; 12–23 = 4; 24–36 = 5). **Nunca 1 ou 2.**
- **Bolsa de Qualificação Profissional**: 1 a 5 parcelas, por **dias de período de desemprego/suspensão** (30–44 = 1; 45–74 = 2; 75–104 = 3; 105–134 = 4; 135–164 = 5).

### 6.4 Prazos para requerer
**Mantido da v1**, incluindo a divergência não resolvida (90 vs. 120 dias para trabalhador formal) — ver Seção 8, item 5 (ambiguidade mantida, não tratada pela auditoria desta rodada).

### 6.5 Valores do benefício
**Mantido da v1** (piso = salário mínimo; teto por tabela de faixas reajustada anualmente; cálculo pela média dos 3 últimos salários). Sem alteração — não contestado pela auditoria.

### 6.6 Suspensão, cancelamento e devolução — **complementado (Falha 2)**
- Suspensão automática por novo vínculo (eSocial/RAIS), bloqueio em 5–15 dias — **mantido da v1**.
- Cancelamento por justa causa — **mantido da v1**.
- **(Novo)** Devolução ao FAT após 67 dias de disponibilização sem saque (Resolução CODEFAT 957/2022) — ver Falha 2/Seção 4-bis.

### 6.7 Canais formais
**Mantido da v1**, sem alteração.

---

## 7. Fail Points Conhecidos, Prováveis ou Recorrentes (lista atualizada)

Os 11 fail points da v1 são **mantidos**. Acrescentam-se:

12. **(Falha 4) Bloqueio de Senha Cidadão por excesso de tentativas incorretas (DTMF/"fat finger") durante a autenticação na URA.** Diferente do fail point já existente na v1 ("não possui senha cadastrada"), este ocorre **com quem já tem senha válida**, mas erra a digitação repetidas vezes — uma interação especialmente propensa a erro no teclado numérico do telefone. Severidade depende da pendência registrada na Seção 8 (desbloqueio remoto vs. presencial).

13. **(Falha 2) Retorno/rejeição de crédito não reconciliado, com janela de 67 dias até devolução ao FAT.** Quando uma parcela "emitida" não chega à conta do cidadão por problema bancário (e não por suspensão/elegibilidade), o cidadão entra em uma janela de até 67 dias em que o problema pode permanecer "invisível" nos status disponíveis (nem "pago", nem claramente "bloqueado por motivo X") — até que, no limite, o direito ao valor daquela parcela específica se perca por devolução ao FAT.

14. **(Novo, decorrente da correção da Falha 1) Risco de informação incorreta sobre número de parcelas por confusão entre modalidades do benefício.** Se a URA (ou um atendente) aplicar a tabela de "1–5 parcelas por dias" (Bolsa de Qualificação Profissional) a um trabalhador formal dispensado sem justa causa — ou vice-versa —, o cidadão recebe uma informação **objetivamente incorreta** sobre quantas parcelas tem direito, o que pode gerar tanto reclamações infundadas (achar que vai receber menos do que tem direito) quanto expectativas infundadas (achar que vai receber 1–2 parcelas quando na verdade não há essa hipótese para sua modalidade).

---

## 8. Pontos Ambíguos, Hipóteses e Lacunas (lista atualizada)

Os 12 itens da v1 são revisados da seguinte forma:

- **Item 6 da v1 ("formulação exata da carência para 3ª solicitação em diante") — RESOLVIDO nesta v2.** Ver Seção 6.2: a redação da Lei nº 13.134/2015 confirma a interpretação restritiva ("cada um dos 6 meses imediatamente anteriores", sem lacunas).
- **Itens 1, 2, 3, 5, 7, 8, 9, 10, 11, 12 da v1 — mantidos sem alteração** (não foram objeto da auditoria nesta rodada; permanecem como lacunas declaradas).
- **Item 4 da v1 ("mecanismo exato de pagamentos a mais durante janela de 5–15 dias") — relacionado, mas distinto, do novo item de devolução ao FAT (67 dias).** Ambos tratam de "dinheiro em trânsito" no backstage, mas por gatilhos diferentes (suspensão por novo vínculo vs. falha de crédito bancário); ambos permanecem pendentes de confirmação de mecanismo exato.

**Novos itens (decorrentes da auditoria):**

15. **(Falha 3a) Existência e conteúdo de norma interna sobre o que a URA pode verbalizar via TTS antes de autenticação completa.** A LGPD fornece o arcabouço de princípios, mas não o roteiro operacional. Resolução exigiria acesso a normas internas de segurança da informação da Caixa/MTE (não públicas) — possivelmente via LAI, com a ressalva de que normas de segurança operacional frequentemente são classificadas e podem não ser passíveis de divulgação integral.

16. **(Falha 3b) Existência e conteúdo do instrumento Caixa–FAT/MTE que rege a função de Agente Pagador, incluindo eventuais SLAs de atendimento.** Resolução exigiria LAI dirigida ao MTE/CODEFAT e/ou à Caixa, solicitando o instrumento vigente (convênio, contrato, ou disciplina específica dentro da Resolução CODEFAT 957/2022) que rege a prestação do serviço de atendimento (não apenas o pagamento em si).

17. **(Falha 4) Caminho de desbloqueio da Senha Cidadão quando o bloqueio ocorre por excesso de tentativas (e não por "esqueci a senha").** Resolução exigiria: (i) ligação de teste real para a URA, deliberadamente errando a senha repetidas vezes, para observar a mensagem e as opções oferecidas; ou (ii) consulta direta à Caixa/documentação interna sobre os dois fluxos distintos ("recadastrar senha" vs. "desbloquear senha por tentativas") — a v1 e a auditoria tratam ambos como equivalentes, mas podem ter regras de resolução diferentes.

18. **(Decorrente da correção da Falha 1) Se a URA (e os atendentes humanos) efetivamente distinguem, no atendimento, entre a modalidade "trabalhador formal/doméstico" e "Bolsa de Qualificação Profissional" ao informar número de parcelas.** Não há evidência pública sobre isso — é uma hipótese de risco (fail point #14) que precisaria ser validada por ligação de teste com um cenário de Bolsa de Qualificação Profissional, se for um público relevante para este serviço.

---

# Parte III — Síntese: Mapeamento para as 5 Camadas do Blueprint (atualizado)

A tabela da v1 (Jornada B — Consulta de status) é **mantida na íntegra como esqueleto**, com as seguintes alterações pontuais:

| Etapa da jornada | Alteração na v2 |
|---|---|
| **3. Autenticação** | Acrescentar, na coluna *Frontstage*: risco de **bloqueio de Senha Cidadão por tentativas** (Falha 4) como desfecho possível desta etapa — ramo que leva a um "beco sem saída" temporário até desbloqueio (caminho de desbloqueio = pendência #17). |
| **4. Consulta de status (eletrônica)** | Acrescentar, na coluna *Backstage*: possibilidade de o status consultado refletir um **retorno/rejeição de crédito em conciliação** (Falha 2 / fail point #13), não apenas "emitida" ou "crédito bloqueado" — ainda que essa distinção provavelmente não seja exposta ao cidadão (ver Evidências Físicas, Seção 2). |
| **6. Atendente humano consulta divergência** | Acrescentar, na coluna *Evidências Físicas/Ações do Cidadão*: se a divergência envolver **número de parcelas** (e não apenas data/valor), atentar para o risco do fail point #14 (confusão entre modalidades do benefício na informação repassada). |
| **9. Resolução eventual** | Acrescentar, na coluna *Backstage/Processos de Suporte*: caminho alternativo — em vez de "Crédito efetivado", o desfecho pode ser **"Crédito devolvido ao FAT após 67 dias"** (Falha 2), caso o cidadão não regularize dados bancários a tempo. Este é um desfecho **negativo** que a v1 não contemplava (a v1 só tinha o desfecho positivo "9. Resolução eventual"). |

Todas as demais etapas (1, 2, 5a, 5b, 7, 8) e suas respectivas colunas **mantêm-se como na v1**, sem alteração.

---

## Anexo — Fontes adicionais consultadas nesta v2 (além das já listadas na v1)

- Texto consolidado da **Lei nº 7.998/1990**, com indicação de redações dadas pela Lei nº 8.900/1994 e pela Lei nº 13.134/2015 (incluindo art. 3º, I, "a/b/c" sobre carência, e art. 2º-A sobre Bolsa de Qualificação Profissional).
- Texto e ementa da **Lei nº 13.134/2015** (alterações ao Programa do Seguro-Desemprego e revogação de dispositivos da Lei nº 7.998/1990 e da Lei nº 8.900/1994).
- Texto e comentários sobre a **Resolução CODEFAT nº 957/2022**, incluindo a regra de **67 dias de disponibilidade para saque / devolução ao FAT** e a tabela de parcelas por dias aplicável à **Bolsa de Qualificação Profissional**.
- Conteúdo confirmando a regra geral de **3 a 5 parcelas conforme tempo trabalhado** para o trabalhador formal (fonte secundária, mas consistente com o texto legal primário consultado).

---

## Resumo executivo das ações tomadas

- **(a) Corrigir**: Falhas 1, 2, 3a (parcial), 4 (parcial), 5 (parcial — framing).
- **(b) Defender**: Falha 5 (parcial — conclusão prática para Jornada C, por razão revisada).
- **(c) Marcar como pendente**: Falha 3a (regras específicas de TTS), Falha 3b (instrumento Caixa–FAT/MTE), Falha 4 (caminho de desbloqueio).

Nenhuma das 5 falhas foi ignorada; todas geraram alteração rastreável na pesquisa (texto novo, fail point novo, normativo novo, ou item de ambiguidade novo/resolvido).
