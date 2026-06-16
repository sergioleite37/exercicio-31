# Resumo Executivo — Service Blueprint AS-IS
## Atendimento ao Seguro-Desemprego pela URA da Caixa Econômica Federal (0800 726 0207)

**Versão:** 2.0 (atualizada) · **Base factual:** `B_relatorio_assistente_v3.md` · **Blueprint completo:** `C_blueprint_asis.md` · **Diagrama:** `D_diagrama_asis.md`

---

## Escopo e estrutura

O canal 0800 726 0207 é procurado para **quatro intenções distintas** que compartilham um único ponto de entrada. O blueprint mapeia as interações efetivas com a Caixa (URA + atendente humano) e os handoffs para o ecossistema externo (MTE, 158, SINE/SRTE, agência, lotérica), **sem expandir para a governança completa do benefício** (FAT/CODEFAT, eSocial, CAGED, RAIS excluídos como atores).

**Ponto de entrada único → 3 ramos após bifurcação de intenção:**

| Ramo | Intenção | Etapas no canal Caixa | Desfecho típico |
|---|---|---|---|
| **A+C** | Solicitar (1ª vez) ou Renovar benefício | 1. Conexão → 2. Identificação → 3. Redirecionamento | Saída verbal para ecossistema MTE — sem resolução no canal Caixa |
| **B** | Consultar benefício já solicitado | 1. Conexão → 2. Identificação → 3. Autenticação → 4. Consulta → 5. Escalonamento | Informação ou orientação; escalonamento frequente para canal externo |
| **D** | Registrar reclamação formal | 1. Conexão → 2. Identificação → 3. Acolhimento + Registro → 4. Encaminhamento | Protocolo gerado; resolução dependente de canais externos |

**Autenticação** (Senha Cidadão 6 dígitos via DTMF) é etapa central do Ramo B — ausente como etapa estrutural nos demais ramos.

---

## 5 achados estruturais

1. **O canal Caixa não tem capacidade resolutiva para a intenção mais frequente.** Os Ramos A+C terminam em redirecionamento verbal ao ecossistema MTE sem protocolo, sem artefato de continuidade e sem rastreabilidade do contato anterior em eventual nova ligação.

2. **A autenticação é o gargalo crítico do Ramo B.** O nó de autenticação se ramifica em três saídas — autenticado, sem senha cadastrada e senha bloqueada —, sendo o terceiro ramo o de **maior risco de severidade subestimada** (★FP3): o caminho de desbloqueio por excesso de tentativas DTMF é indeterminado (remoto vs. presencial), podendo converter uma consulta de rotina em ruptura total do canal remoto.

3. **A consulta concentra o maior núcleo de risco pós-autenticação.** Quatro fail points simultâneos (⚠5 divergência de status, ⚠6 janela de 67 dias invisível, ⚠7 mensagens genéricas, ⚠8 falhas em lote) mais o risco de informação errônea sobre parcelas (⚠11) incidem na mesma etapa. A integração Caixa↔MTE tem mecanismo indeterminado (batch vs. tempo real), tornando a divergência de status estrutural, não acidental.

4. **O escalonamento é antecâmara de saída, não de resolução.** A transferência para atendente humano não resolve — é estruturalmente uma transição para fora do canal, com risco adicional de queda de chamada sem callback (⚠2) e empurra-empurra institucional Caixa↔MTE (⚠9) quando a causa-raiz é de competência do MTE.

5. **Há uma ausência crítica de artefatos de continuidade.** O aviso de prazo de 67 dias para devolução ao FAT não existe como evidência física no canal (marcado como ~~ausência~~ na consulta). Cidadãos redirecionados nos Ramos A+C saem sem protocolo ou comprovante (⚠1). Cidadãos em escalonamento não recebem confirmação de posição em fila nem callback em caso de desconexão (⚠2).

---

## 11 fail points mapeados — por severidade

| Sev. | # | Fail point | Ramo | Etapa |
|---|---|---|---|---|
| ★ Crítica | FP3 | Bloqueio de Senha Cidadão por tentativas DTMF — destino de desbloqueio **indeterminado** | B | Autenticação |
| Alta | FP1 | Canal errado para iniciar — redirecionamento sem resolução nem protocolo | A+C | Redirecionamento |
| Alta | FP2 | Queda de ligação antes do atendente, sem callback automático | B | Escalonamento |
| Alta | FP4 | Dependência de etapa presencial obrigatória (lotérica) para cadastro/regularização de senha | B | Autenticação |
| Alta | FP5 | Divergência de status entre sistemas Caixa e MTE — múltiplas visões dos mesmos dados | B | Consulta |
| Alta | FP6 | Retorno/rejeição de crédito com janela de até 67 dias até devolução ao FAT — invisível ao cidadão | B | Consulta |
| Alta | FP8 | Falhas sistêmicas em lote (ex.: jun/2025) com comunicação defasada — amplifica FP6 | B | Consulta |
| Alta | FP9 | Empurra-empurra institucional Caixa↔MTE — repasse de responsabilidade sem resolução | B+D | Escalonamento |
| Alta | FP10 | Prazo de requerimento perdido — cidadão fora da janela 7–120 dias não pode ser habilitado | A+C | Redirecionamento |
| Alta | FP11 | Confusão entre faixas de parcelas por nº de solicitação — risco de informar direito inexistente | B | Consulta |
| Média | FP7 | Mensagens genéricas de erro — não acionáveis, sem causa-raiz nem direcionamento | B | Consulta |

---

## Atores e responsabilidades (síntese RACI)

| Ator | Papel central | Limite de alçada |
|---|---|---|
| **URA Caixa Cidadão** | Responsável pelo frontstage das etapas universais e do Ramo A+C inteiro; autenticação no Ramo B | Não distingue contextos individuais além do backend; não resolve solicitação/renovação por design |
| **Atendente Humano Caixa** | Julgamento situacional no Ramo B (consulta) e Ramo D (reclamação); gera protocolo | Sem alçada quando causa-raiz é do MTE (FP9) |
| **Backstage Caixa** | Autoridade técnica sobre autenticação, consulta (SISGR) e reclamações | Depende de dados MTE; responsável pelo bloqueio antifraude (★FP3) |
| **MTE (externo)** | Origem dos dados de habilitação; destino dos cidadãos redirecionados | Sem presença direta no canal Caixa; integração com mecanismo indeterminado |

*Tabela RACI completa com mapeamento R/A/C/I por etapa disponível em `C_blueprint_asis.md`.*

---

## Pré-condições para finalização do blueprint

| Prioridade | Item em aberto | Método de resolução |
|---|---|---|
| **1 — Crítico** | Caminho de desbloqueio da Senha Cidadão (★FP3): remoto ou obrigatoriamente presencial? | Ligação de teste com erros deliberados de DTMF; ou consulta à documentação interna Caixa distinguindo "recadastro" de "desbloqueio por tentativas" |
| **2 — Alto** | Árvore real de menus da URA: estrutura exata, voz vs. DTMF, ponto de coleta de credenciais | Shadowing / ligação de teste real |
| **3 — Médio** | Mecanismo de sincronização Caixa↔MTE: batch vs. tempo real | Acesso institucional direto ou LAI ao MTE/Caixa |
